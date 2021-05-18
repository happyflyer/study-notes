# Win 环境 IDEA 配置

- 修改 `bin/idea64.exe.vmoptions`

```properties
-Xms4g
-Xmx4g
-XX:ReservedCodeCacheSize=2g
-XX:+UseG1GC
-XX:SoftRefLRUPolicyMSPerMB=50
-XX:CICompilerCount=2
-XX:+HeapDumpOnOutOfMemoryError
-XX:-OmitStackTraceInFastThrow
-ea
-Dsun.io.useCanonCaches=false
-Djdk.http.auth.tunneling.disabledSchemes=""
-Djdk.attach.allowAttachSelf=true
-Djdk.module.illegalAccess.silent=true
-Dkotlinx.coroutines.debug=off
-Duser.name=lifei
```
