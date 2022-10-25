[HOME](Home)
# SDWL Library Interface #


## Interfaces ##
```c
DWORD SDWLibGetVersion(void);
```
>This function returns the version number of the module.
>the format of version is AABBCCCC major.minor.build

```c
SDWLResult SDWLibCreateSDRmcSession(WCHAR * tempfolder , ISDRmcSession ** pSession); 
```
>This function creates ISDRmcSession instance.

>[in]tempfolder	fullpath of temporary folder for RmcAPI
>[out] pSession	ISDRmcSession instance. if ISDRmcSession pointer is NULL, check return result;

>Note: **SDWLibDeleteRmcSession must be called to delete this instance !!!** Otherwise, it will cause memory leak

```c
void SDWLibDeleteRmcSession(ISDRmcSession	*pSession);
```
>This function deletes ISDRmcSession instance
>[in] pSession          a pointer to ISDRmcSession instancereturn from SDWLibrCreateSDRmcSession