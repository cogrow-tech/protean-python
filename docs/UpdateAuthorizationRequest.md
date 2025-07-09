# UpdateAuthorizationRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**resource_id** | **str** | Identifies the resource whose authorization will be updated. | [optional] 
**resource_type** | **str** | Type of resource whose authorization will be updated. | [optional] 
**owner_users** | [**List[EmbeddableUser]**](EmbeddableUser.md) | Users who have ownership of the resource. | [optional] 
**owner_groups** | **List[str]** | Groups who have ownership of the resource. | [optional] 
**viewer_users** | [**List[EmbeddableUser]**](EmbeddableUser.md) | Users who can use of the resource. | [optional] 
**viewer_groups** | **List[str]** | Groups who can use of the resource. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


