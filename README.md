sudo chown -R 10001:65533 verdaccio/storage
sudo chmod -R u+rwX,go+rX verdaccio/storage

sudo chown -R 10001:65533 verdaccio
sudo find verdaccio -type d -exec chmod 755 {} \;
sudo find verdaccio -type f -exec chmod 644 {} \;

docker compose up -d verdaccio nginx
docker compose run --rm preload
