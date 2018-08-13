# Summary

Business, corporate, and purchasing cards are used just like personal credit and debit cards. However, these cards carry higher interchange rates because they offer employers high value (and costly) features such as enhanced reporting and statements. Many merchants can qualify for lower commercial rates by collecting the more in‑depth Level 2 and Level 3 data with each commercial card transaction.

See [Level 2 and Level 3 Fields](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Level%202%20and%20Level%203%20Fields.md ) to understand what is level 2 and level 3 fields and how PayFabric support your business to integrate.

PayFabric is helping merchants avoid incautious downgrading by supporting merchants setup default value for some of level 2 and level 3 fields. Navigate through **Settings** > **existing gateway account profile block** > L2/3 Fields Default, you will open below screen.

![l23default](https://s3-us-west-1.amazonaws.com/github-screenshot-repository/V3/L2%263+Fields+Default.png)

# Details

## Gateway Specific

**L2/3 Fields Default** is  only available on the gateway profile whose **Card Class** is 'Credit'. 

## Applying Logic

There're two ways to apply the default fields:

1. **Apply PayFabric's default values to all fields with missing Level 2/3 data**. By choosing this option, default values will be submitted to gateway when application doesn't send any level 2/3 data to PayFabric.

2. **Ignore PayFabric's default values if Level 2/3 data is not submitted from application**. By choosing this option, default values will **NOT** be submitted to gateway when application doesn't send any level 2/3 data to PayFabric.

Note: If application send at least one value of level 2/3 data to PayFabric, both options will apply the default values for the fields omitted by application.
