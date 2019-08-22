1. Let's use our Drupal compose file from assignment (docker-compose/assignment-2)
2. Rename image back to official **drupal:8.2**
3. Remove **build:**
4. Add secret via **external:**
5. use environment variable **POSTGRES_PASSWORD_FILE**
6. Add secret via cli **echo "\<pm>" | docker secret create psql-pw -**
7. Copy compose into a new yml file on your Swarm node1