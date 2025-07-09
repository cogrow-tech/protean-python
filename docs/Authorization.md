# Authorization


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Identifies the resource to which the authorization details apply. | [optional] 
**resource_type** | **str** | Type of resource to which the authorization details apply. | [optional] 
**owner_users** | [**List[EmbeddableUser]**](EmbeddableUser.md) | Users who have ownership of the resource. | [optional] 
**owner_groups** | **List[str]** | Groups who have ownership of the resource. | [optional] 
**viewer_users** | [**List[EmbeddableUser]**](EmbeddableUser.md) | Users who can use of the resource. | [optional] 
**viewer_groups** | **List[str]** | Groups who can use of the resource. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


