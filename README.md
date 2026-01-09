🧠 TalentLink AI - Backend APIThis is the core intelligence engine for the TalentLink AI recruitment platform. It handles multi-format resume parsing, AI-driven candidate ranking, and secure document management.

🛠️ Tech StackFramework: Spring Boot 3.xLanguage: Java 17+Database: PostgreSQLORM: Spring Data JPA (Hibernate)Intelligence: (Mention your AI API here, e.g., OpenAI/Gemini integration)Build Tool: Maven

🚀 Key FeaturesSemantic Search: Advanced JPQL queries with case-insensitive search and explicit type casting for PostgreSQL bytea compatibility.Optimized DTO Projections: Custom DTOs used for high-performance listing to avoid heavy LOB (Large Object) memory overhead.Automated AI Dossier: Logic to extract and store professional summaries, technical skills, and match justifications.RESTful API Design: Clean, resource-based endpoints for Job and Resume management.

📁 Project StructurePlaintextsrc/main/java/com/talentlink/api/
├── controller/  # REST Endpoints
├── service/     # Business Logic & AI Integration
├── repository/  # Database Queries (Spring Data JPA)
├── dto/         # Lightweight Data Transfer Objects
├── model/       # JPA Entities (Job, Resume)
└── exception/   # Global Error Handling


⚙️ Local Setup1. PrerequisitesJDK 17 or higherPostgreSQL installed and runningMaven2. 
Configure DatabaseUpdate src/main/resources/application.
properties with your local credentials:
Propertiesspring.datasource.url=jdbc:postgresql://localhost:5432/talentlink_db

spring.datasource.username=your_username

spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update

3. Run the ApplicationBashmvn spring-boot:run

The API will be available at http://localhost:8080/api.

📡 API Endpoints (Quick Reference)MethodEndpointDescriptionGET/api/jobsRetrieve all hiring projectsGET/api/resumes/job/{id}Search/List candidates for a jobGET/api/resumes/{id}Get full AI analysis for a resumePOST/api/resumes/uploadUpload and process a new resumeDELETE/api/jobs/{id}Remove job and all associated resumes

🔒 Security & PerformanceCORS Configuration: Configured to allow secure requests from the Angular frontend.Resource Cleanup: Implemented ON DELETE CASCADE at the database level for efficient data hygiene.PostgreSQL Casting: Handles LOWER(CAST(column AS text)) to ensure robust search across various data types.
