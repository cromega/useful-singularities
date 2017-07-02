# Backup to AWS bucket

## Deps

1. Create a versioned S3 bucket (or a non-versioned one but then you have to use filenames with a date)
1. Create a user that has access to this bucket

## Build

1. Edit the bootstrap file and fill in the credentials
1. Create the container

```
singularity create -s 128 backup-to-aws.img
sudo singularity bootstrap backup-to-aws.img backup-to-aws.bs
```

## Back things up

```
tar -cjO /var/spool/mail | singularity exec backup-to-aws.img s3 cp - s3://bucket/emails.tar.bz2
```

## etc

It's also a great way of installing the aws-cli without littering your system with all the python crap.

```
alias aws="singularity exec backup-to-aws.img aws"
```
