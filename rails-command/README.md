build:

```
docker build --platform linux/x86_64 -t gcr.io/PROJECT_ID/rails-command .
```

push:

```
docker push gcr.io/PROJECT_ID/rails-command:latest
```

deploy:

```
gcloud beta run jobs create rails-command \
        --image gcr.io/PROJECT_ID/rails-command \
        --command bin/rails \
        --args about \
        --tasks 1 \
        --max-retries 0
```

or

```
gcloud beta run jobs update rails-command \
        --image gcr.io/PROJECT_ID/rails-command \
        --command bin/rails \
        --args about \
        --tasks 1 \
        --max-retries 0
```

execute:

```
gcloud beta run jobs execute rails-command
```
