go mod init github.com/__/ama-go
tern init ./internal/store/pgstore/migrations     
tern new --migrations ./internal/store/pgstore/migrations create_rooms_table
tern new --migrations ./internal/store/pgstore/migrations create_messages_table 

go mod tidy

sqlc generate -f ./internal/store/pgstore/sqlc.yaml  

go generate ./...