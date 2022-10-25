# SDWL library interface for SkyDRM Session #

```c
virtual SDWLResult Initialize(std::wstring router, std::wstring tenant) = 0;
```
	/// Initialize RMCSession Class
	/**
	 * @pre
	 *    Call API function SDWLibCreateSDRmcSession to obtain handle of RMCSession Class
	 * @param
	 *    router	router URL for registered tenant. if empty, default value will be used.
	 *    tenant	tenant id string. if empty, default value will be used
	 * @return
	 *    Result: return RESULT(0) when success
	 *			SDWL_CERT_NOT_READY			certificate is not installed/fail to installed
	 *			SDWL_RMS_ERRORCODE_BASE+	RMS server error
	 */
```c
virtual SDWLResult Initialize(std::wstring workingfolder, std::wstring router, std::wstring tenant) = 0;
```
	/// Initialize RMCSession Class
	/**
	* @pre
	*    Call API function SDWLibCreateSDRmcSession to obtain handle of RMCSession Class
	* @param
	*    workingfolder	file folder string to save SDWLSession internal data files. if no working folder is set
	*					the data files will be saved at temporary folder set at SDWLibCreateSDRmcSession() 
	*    router			router URL for registered tenant. if empty, default value will be used.
	*    tenant			tenant id string. if empty, default value will be used
	* @return
	*    Result: return RESULT(0) when success
	*			SDWL_PATH_NOTFOUND			invalid working folder
	*			SDWL_CERT_NOT_READY			certificate is not installed/fail to installed
	*			SDWL_RMS_ERRORCODE_BASE+	RMS server error
	*/
```c
virtual SDWLResult Save(std::wstring folder = L"") = 0;
```
	/// Save SDWLSession internal data files to specified folder
	/**
	 * @pre
	 *    Intialize() function need be called before calling this funciton
	 * @param 
	 *    folder		file folder string to save SDWLSession internal data files. if no working folder is set
	 *					the data files will be saved at temporary folder set at SDWLibCreateSDRmcSession().
	 *					if empty, the workingfolder or temporary folder will be used.
	 *					Note: if no working folder is set, only tenant related information will be saved.
	 * @return
	 *			SDWL_PATH_NOTFOUND			invalid working folder
	 */
};