build:

```
gcloud builds submit --pack image=gcr.io/PROJECT_ID/scheduled-hello
```

deploy:

```
gcloud beta run jobs create scheduled-hello \
    --image gcr.io/PROJECT_ID/scheduled-hello \
    --tasks 1
```

or

```
gcloud beta run jobs update scheduled-hello \
    --image gcr.io/PROJECT_ID/scheduled-hello \
    --tasks 1
```

execute:

```
gcloud beta run jobs execute scheduled-hello
```

schedule:

```
gcloud scheduler jobs create http scheduled-hello \
  --location SCHEDULER_REGION \
  --schedule="SCHEDULE" \
  --uri="https://CLOUD_RUN_REGION-run.googleapis.com/apis/run.googleapis.com/v1/namespaces/PROJECT-ID/jobs/scheduled-hello:run" \
  --http-method POST \
  --oauth-service-account-email PROJECT-NUMBER-compute@developer.gserviceaccount.com
```
