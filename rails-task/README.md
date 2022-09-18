build:

```
docker build --platform linux/x86_64 -t gcr.io/PROJECT_ID/rails-task .
```

push:

```
docker push gcr.io/PROJECT_ID/rails-task:latest
```

deploy:

```
gcloud beta run jobs create rails-task \
        --image gcr.io/PROJECT_ID/rails-task \
        --command bin/rails \
        --args about \
        --tasks 1 \
        --max-retries 0
```

or

```
gcloud beta run jobs update rails-task \
        --image gcr.io/PROJECT_ID/rails-task \
        --command bin/rails \
        --args about \
        --tasks 1 \
        --max-retries 0
```

execute:

```
gcloud beta run jobs execute rails-task
```
