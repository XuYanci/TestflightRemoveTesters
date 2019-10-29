### Needed

  1. You Must Get ISSUSER_ID、KEY_DIR(存放下载的p8)、KEY_ID、APP_ID 

  2. Use XCToken To Generate The Token


### Progress

  1. 根据BundleID,BetaGroup名称获取到群组信息 (*这里有可能还有多个同名的测试群组)
https://api.appstoreconnect.apple.com/v1/betaTesters?filter[app]=123456789&filter[name]=BetaGroup

GROUPINFO:

<code>
  "data": [
        {
            "type": "betaGroups",
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        }
    ]
</code>

  2. 根据群组ID获取测试人员名单
https://api.appstoreconnect.apple.com/v1/betaGroups/#{specify_group_id}/relationships/betaTesters


  3. 获取测试人员名单后，我们需要从BetaGroup中删除用户，只需要调用 DELETE ,然后提交需要删除的成员信息 (步骤2)
https://api.appstoreconnect.apple.com/v1/betaGroups/#{specify_group_id}/relationships/betaTesters


### References:

https://github.com/XCTEQ/XCToken

https://developer.apple.com/documentation/appstoreconnectapi/

