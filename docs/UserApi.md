# UserApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_user_profile**](UserApi.md#get_user_profile) | **GET** /api/auth-service/users/me/profile | Get authenticated user&#39;s profile.


# **get_user_profile**

Retrieve currently authenticated user's profile.


### Parameters
Input examples could be found [here](UserApiExamples.md#get_user_profile).

This endpoint does not need any parameter.

### Return type

[**User**](User.md)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

