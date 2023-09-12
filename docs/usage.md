For more information about the API (params, columns), see
the [API](https://business-api.tiktok.com/portal/docs?id=1735713875563521).

# APIs

## Get report

```python
from bi_tiktok_business_api_master import TikTokBusinessClient

credentials_path = '/home/credentials.json'

advertiser_ids = TikTokBusinessClient.get_advertiser_ids(credentials_path)
client = TikTokBusinessClient.from_json_file(advertiser_id=advertiser_ids[0],
                                             json_file_path=credentials_path)
report = client.report.get_synchronous_report(
    {
        "report_type": "BASIC",
        "data_level": "AUCTION_ADGROUP",
        "dimensions": ["stat_time_day", "country_code", "adgroup_id"],
        "metrics": ["spend", "impressions", "clicks", "conversion", "app_install"],
        'start_date': '2023-09-03',
        'end_date': '2023-09-06',
    }
)

print(report)
```

## Get ad groups of an advertiser

```python
from bi_tiktok_business_api_master import TikTokBusinessClient

credentials_path = '/home/credentials.json'

advertiser_ids = TikTokBusinessClient.get_advertiser_ids(credentials_path)
client = TikTokBusinessClient.from_json_file(advertiser_id=advertiser_ids[0],
                                             json_file_path=credentials_path)

ad_groups = client.ad_group.get_ad_groups(
    {
        'fields': [
            "create_time",
            "campaign_id",
            "campaign_name",
            "adgroup_id",
            "adgroup_name",
            "app_id",
            "app_download_url"
        ]
    }
)
```
