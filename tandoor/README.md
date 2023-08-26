Docker String

docker run -d \
    -v "$(pwd)"/staticfiles:/opt/recipes/staticfiles \
    -v "$(pwd)"/mediafiles:/opt/recipes/mediafiles \
    -p 80:8080 \
    -e SECRET_KEY=another_fake_key\
    -e DB_ENGINE=django.db.backends.postgresql \
    -e POSTGRES_HOST=db_recipes \
    -e POSTGRES_PORT=5432 \
    -e POSTGRES_USER=djangodb \
    -e POSTGRES_PASSWORD=fake_key\
    -e POSTGRES_DB=djangodb \
    --name recipes_1 \
    vabene1111/recipes