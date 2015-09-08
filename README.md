# chef-data
Chef data management cookbook.

There are several ways to specify where to get data (like secrets, usernames, etc).

To make it easy to locate and load data, it'd be great to have a data URI scheme.

Some examples:

```
get_data_uri('node://java/version') #=> returns the contents of node['java']['version']

get_data_uri('data-bag://satchel/front-pocket') #=> returns the value of Chef::DataBagItem.load('satchel', 'front-pocket')

get_data_uri('data-bags://bank/deposit-box') #=> returns the value of Chef::EncyptedDataBagItem.load('bank', 'deposit-box')

get_data_uri('data-bags://bank/%name%') #=> returns the value of Chef::EncyptedDataBagItem.load('bank', node.name)
```
