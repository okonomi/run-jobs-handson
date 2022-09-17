build:

```
gcloud builds submit --pack image=gcr.io/PROJECT_ID/hello
```

deploy:

```
gcloud beta run jobs create hello \
    --image gcr.io/PROJECT_ID/hello \
    --tasks 1
```

or

```
gcloud beta run jobs update hello \
    --image gcr.io/PROJECT_ID/hello \
    --tasks 1
```

execute:

```
gcloud beta run jobs execute hello
```
