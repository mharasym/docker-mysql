# docker-mysql
If you prefer using docker based environment (e.g., laravel/sail) while developing your projects, in some cases you may need to use single database for multiple projects. In such case consider this solution:

1) Clone && cd this repo, then run
```
cp .env.example .env
docker-compose up -d
```
2) In related projects add to the **docker-compose.yml** networks section additional network:
```
networks:
    mysqlx_network:
        external: true
```
3) Now you may use **DB_HOST=mysqlx** in .env files of related projects