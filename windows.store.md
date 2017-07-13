# Windows Store


Linking via URL's of the format `www.microsoft.com/store/apps/DEADBEEFGH67X3F`

```bash
find ../.. -name "Package.StoreAssociation.xml" -exec ls {} \; -exec grep LandingUrl {} \;

../../DEADBEEF/AnnotationZoningTool/AnnotationZoningTool/Package.StoreAssociation.xml
  <PackageInfoList LandingUrl="https://developer.microsoft.com/dashboard/Application?appId=DEADBEEFF15RC" />
  
```