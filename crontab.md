### Open crontab
`crontab -e`

### For Production Server
```
*/2 * * * * aws s3 sync --delete /var/www/html/wp-content/uploads s3://<BucketNameForMedia>
*/2 * * * * aws s3 sync --delete /var/www/html/ s3://<BucketNameForCode>
```

### For Disaster Recovery Server
```
*/2 * * * * aws s3 sync --delete s3://<BucketNameForMedia> /var/www/html/wp-content/uploads
*/2 * * * * aws s3 sync --delete s3://<BucketNameForCode> /var/www/html/
```
