## 1. API Description

This API (DeleteSubnet) is used to delete subnets.
Domain for API request:<font style="color:red">vpc.api.qcloud.com</font> 

You need to remove all resources (including CVMs, cloud load balancers, cloud data, noSql and so on) under the subnet before you can delete it.

## 2. Input Parameters
The following request parameter list only provides API request parameters. Common request parameters need to be added when the API is called. For more information, refer to <a href="/doc/api/372/4153" title="Common request parameters">Common Request Parameters</a>. The Action field for this API is DeleteSubnet.

| Parameter Name | Required | Type | Description |
|---------|---------|---------|---------|
| vpcId | Yes | String | Virtual private cloud ID of the subnet, which can be vpcId or unVpcId. unVpcId is recommended. For example: vpc-kd7d06of. You can query this through API <a href="http://cloud.tencent.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E7%A7%81%E6%9C%89%E7%BD%91%E7%BB%9C%E5%88%97%E8%A1%A8" title="DescribeVpcEx">DescribeVpcEx</a>.  |
| subnetId | Yes | String | ID of the subnet to be deleted. Both subnetId and unSubnetId are supported. unSubnetId is recommended. For example: subnet-k20jbhp0. You can query this through the API <a href="http://cloud.tencent.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E5%AD%90%E7%BD%91%E5%88%97%E8%A1%A8" title="DescribeSubnetEx">DescribeSubnetEx</a>.  |


## 3. Output Parameters

| Parameter Name | Type | Description |
|---------|---------|---------|
| code | Int | Common error code; 0: Succeeded; other values: Failed. For more information, please refer to <a href="https://intl.cloud.tencent.com/document/product/215/4781" title="Common Error Codes">Common Error Codes</a> on the Error Code page. |
| message | String | Module error message description depending on API. |

 ## 4. Error Code Table
 The following error code list only provides the business logic error codes for this API. For additional common error codes, refer to <a href="https://cloud.tencent.com/doc/api/245/4924" title="VPC Error Codes">VPC Error Codes</a>.

| Error Code | Description |
|---------|---------|
| InvalidVpc.NotFound | Invalid VPC. VPC resource does not exist. Please verify that the resource information you entered is correct. You can query the VPC via the API <a href="http://cloud.tencent.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E7%A7%81%E6%9C%89%E7%BD%91%E7%BB%9C%E5%88%97%E8%A1%A8" title="DescribeVpcEx">DescribeVpcEx</a>.  |
| InvalidSubnet.NotFound | Invalid subnet. Subnet resource does not exist. Please verify that the resource information you entered is correct. You can query subnets via the API <a href="http://cloud.tencent.com/doc/api/245/%E6%9F%A5%E8%AF%A2%E5%AD%90%E7%BD%91%E5%88%97%E8%A1%A8" title="DescribeSubnetEx">DescribeSubnetEx</a>.  |
| InvalidSubnet.CannotDelete | Cannot delete the subnet because there are still resources under this subnet.  |

## 5. Example
 
Input
<pre>
  https://vpc.api.qcloud.com/v2/index.php?Action=DeleteSubnet
	&<<a href="https://cloud.tencent.com/doc/api/229/6976">Common request parameters</a>>
  &vpcId=vpc-kd7d06of
  &subnetId=subnet-k20jbhp0
</pre>

Output
```
{
    "code": 0,
    "message": ""
}

```


