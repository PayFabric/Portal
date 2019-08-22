# Summary

Business, corporate, and purchasing cards are used just like personal credit and debit cards. However, these cards carry higher interchange rates because they offer employers high value (and costly) features such as enhanced reporting and statements. Many merchants can qualify for lower commercial rates by collecting more in‑depth Level 2 and Level 3 data with each commercial card transaction.

See [Level 2 and Level 3 Fields](https://github.com/PayFabric/APIs/blob/master/PayFabric/Sections/Level%202%20and%20Level%203%20Fields.md ) to understand what is level 2 and level 3 fields and how PayFabric support your business to integrate.

PayFabric is helping merchants achieve better transaction rate by supporting merchants submitting level 2 and 3 data during transaction processing. In additions, PayFabric allows merchants to setup default value for supported level 2 and level 3 fields. 

When the [Design Mode](PayFabric%20Settings.md#design-mode) is **Legacy Design**, Navigate through **Settings** > **Gateway Account Configuration** > **existing gateway account profile block** > L2/3 Fields Default, you will open below screen.

![l23default](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/L2%263%20Fields%20Default.png)

When the [Design Mode](PayFabric%20Settings.md#design-mode) is **Modern Design**, Navigate through **Settings** > **Gateway Account Configuration** > **existing gateway account profile block** > L2/3 Fields Default, you will open below screen. Merchants are able to set up different Level 2 & Level 3 default values for VISA and Mastercard respectively. 

![l23defaultbycardtypes](https://raw.githubusercontent.com/PayFabric/Portal/master/PayFabric/Sections/Screenshots/L2%263%20Fields%20Default%20by%20Card%20Types.png)

# Details

## Gateway Specific

**L2/3 Fields Default** is  only available on the gateway profile whose **Card Class** is 'Credit'. 

## Applying Logic

There're two ways to apply the default fields:

1. **Apply PayFabric's default values to all fields with missing Level 2/3 data**. By choosing this option, default values will be submitted to gateway when application doesn't send any level 2/3 data to PayFabric.

2. **Apply PayFabric's default values at all times**. By choosing this option, default values will be submitted to gateway at all times.
