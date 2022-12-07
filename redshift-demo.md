

1. datalake, glue, athena concept

/Users/kiwony/Documents/00.SessionDeck/20221115.KAL.QS.ADV

00-Glue_Athena_QuickSight.pptx



2. DMS Concept

01.DMS-Session.pptx



3. Handson 시나리오 설명

https://github.com/kiwonyoon0701/datalake-workshop/blob/master/00.md

## bit.ly/kal-20221115



4. Redshift Unload & QS 연동 시연

- IAM Role 설명
- unload 시연

```
unload ('select * from customer')   
to 's3://redshift-unload-20221115/raw/' 
iam_role 'arn:aws:iam::704631266360:role/redshift-s3-role'
parquet 
maxfilesize 1 gb;
```

```
unload ('select * from customer')   
to 's3://redshift-unload-20221115/raw/' 
iam_role 'arn:aws:iam::704631266360:role/redshift-s3-role'
parquet 
maxfilesize 100 mb;
```

```
unload ('select count(c_nationkey),c_nationkey from customer group by c_nationkey')   
to 's3://redshift-unload-20221115/customer-nkey-groupby/' 
iam_role 'arn:aws:iam::704631266360:role/redshift-s3-role' 
csv
maxfilesize 5 mb;
```

```
select count(a.c_custkey),b.n_name from customer a, nation b where a.c_nationkey=b.n_regionkey group by b.n_name;
```



-  unload option

https://docs.aws.amazon.com/redshift/latest/dg/t_Unloading_tables.html

















