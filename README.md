

https://github.com/user-attachments/assets/371c2aa3-1dff-406a-b9a7-6962a59c226f

Conclusion :
Le test de charge a montré que seules les copies disponibles ont pu être empruntées avec succès, et que les requêtes excédentaires ont généré des conflits, confirmant la bonne gestion du stock. Le curl /api/books a confirmé que le stock final était à zéro, garantissant l’intégrité des données. Lors de l’arrêt du service pricing, le fallback a été déclenché, retournant un prix par défaut de 0.0, démontrant la robustesse de l’application. Les métriques exposées via /actuator/metrics confirment que Resilience4j surveille bien le circuit breaker et les appels protégés. L’usage d’un verrou DB est crucial en multi-instances pour éviter les problèmes de concurrence et garantir qu’une même copie n’est pas empruntée simultanément par plusieurs services, tandis que le circuit breaker et le fallback assurent la résilience du système face aux pannes d’un service externe.
