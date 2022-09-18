build:

```
docker build --platform linux/x86_64 -t gcr.io/PROJECT_ID/arguments .
```

push:

```
docker push gcr.io/PROJECT_ID/arguments:latest
```

deploy:

```
gcloud beta run jobs create arguments \
        --image gcr.io/PROJECT_ID/arguments \
        --args aa,bb,cc \
        --tasks 1
```

or

```
gcloud beta run jobs update arguments \
        --image gcr.io/PROJECT_ID/arguments \
        --args aa,bb,cc \
        --tasks 1
```

execute:

```
gcloud beta run jobs execute arguments
```
