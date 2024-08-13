USER1_TOKEN=$(docker exec krakend-designer curl -s -d "client_id=mockbin-app" -d "username=mockbin-app-user1" -d "password=secret" -d 'grant_type=password' http://keycloak:8080/realms/demo/protocol/openid-connect/token | jq -r '.access_token')

USER2_TOKEN=$(docker exec krakend-designer curl -s -d "client_id=mockbin-app" -d "username=mockbin-app-user2" -d "password=secret" -d 'grant_type=password' http://keycloak:8080/realms/demo/protocol/openid-connect/token | jq -r '.access_token')

curl -v http://localhost:8402/mockbin

curl -v -H "Authorization: Bearer $USER1_TOKEN" http://localhost:8402/mockbin

curl -v -H "Authorization: Bearer $USER2_TOKEN" http://localhost:8402/mockbin

for _ in {1..10} ; do curl -v -H "Authorization: Bearer $USER1_TOKEN" http://localhost:8402/mockbin ; done