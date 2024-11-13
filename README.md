# 🏥 Plateforme de Santé en Ligne

Ce projet de plateforme de santé en ligne utilise une **architecture microservices** pour offrir une flexibilité, une scalabilité et une sécurité renforcées. Construit avec **Spring Boot** pour les services backend, **Spring Cloud** pour la gestion des microservices, et **React.js** pour l’interface utilisateur frontend, le système est structuré de façon modulaire, avec chaque service gérant une fonction spécifique. La communication entre les microservices est assurée par des **API REST** et **Kafka** pour la gestion de la communication asynchrone, permettant un flux de données en temps réel et une gestion fiable des événements. L’**API Gateway** et le **registre de services Eureka** permettent le routage et la découverte des services.

### Objectif du Projet
Cette plateforme de santé a pour but de fournir aux **patients** et **praticiens** un accès pratique aux consultations médicales, à la prise de rendez-vous et aux paiements en ligne. L'architecture microservices permet une gestion efficace des processus métier et des mises à jour continues, sans interruption de service.

### Architecture et Services
| Service                | Fonction                                                                                   | Technologie(s)                           | Communication                                  |
|------------------------|--------------------------------------------------------------------------------------------|------------------------------------------|------------------------------------------------|
| **API Gateway**        | Point d'entrée unique pour les utilisateurs.                                               | Spring Cloud Gateway                     | Gère les demandes via des API REST             |
| **Service Registry**   | Enregistrement et découverte des services.                                                 | Eureka Server (Spring Cloud Netflix)     | Facilite la communication entre microservices  |
| **User Service**       | Gère l'authentification et les profils utilisateurs.                                       | Spring Boot, Spring Security, JWT        | Avec Booking, Consultation, et Billing Service |
| **Booking Service**    | Gère les réservations. Vérifie les disponibilités et confirme les paiements.               | Spring Boot, MongoDB                     | Avec User, Consultation, Payment, Notification |
| **Consultation Service** | Facilite les consultations en ligne et gère les créneaux disponibles.                   | Spring Boot, Kafka                       | Avec Booking, User, Reporting Service          |
| **Payment Service**    | Gère les transactions de paiement.                                                         | Spring Boot, Stripe/PayPal intégration   | Avec Billing, Notification, Booking Service    |
| **Billing Service**    | Gère la facturation et émet les factures.                                                  | Spring Boot, MySQL                       | Avec Payment, User, Notification Service       |
| **Notification Service** | Envoie les notifications (confirmations, rappels).                                      | Spring Boot, Kafka                       | Avec Booking, Payment, Consultation, Billing   |
| **Reporting Service**  | Produit des rapports d'activité et analyses.                                               | Spring Boot, MongoDB                     | Avec Consultation, Billing, User Service       |

### 🛠 Technologies Utilisées
- **Backend** : Spring Boot pour chaque microservice, Spring Cloud pour la gestion des services (Gateway, Eureka)
- **Frontend** : React.js pour l'interface utilisateur
- **Bases de données** : MongoDB (données de réservation et consultation), MySQL (facturation)
- **API** : RESTful API pour la communication entre services
- **Message Queue** : Kafka pour la communication asynchrone entre services
- **Sécurité** : JWT pour l'authentification

---

![Description du projet](description.png)
