# graal-vm-flags
My personal GraalVM set of flags dedicated for Minecraft Server, based on Aikars's flags and with the addition of GraalVM Enterprise optimization flags 

___
# The Flags:

***java -Xms[A number]G -Xmx[That same number]G***`-XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=130 -XX:ConcGCThreads=2 -XX:+UnlockExperimentalVMOptions -XX:+UnlockDiagnosticVMOptions -XX:+DisableExplicitGC -XX:G1NewSizePercent=40 -XX:G1MaxNewSizePercent=50 -XX:G1HeapRegionSize=16M -XX:G1ReservePercent=15 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=3 -XX:InitiatingHeapOccupancyPercent=20 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=0 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://mcflags.emc.gs/ -XX:UseAVX=3 -XX:+UseStringDeduplication -XX:+UseFastUnorderedTimeStamps -XX:+UseAES -XX:+UseFMA -XX:+UseAESIntrinsics -XX:UseSSE=4 -XX:AllocatePrefetchStyle=1 -XX:+UseLoopPredicate -XX:+RangeCheckElimination -XX:+EliminateLocks -XX:+DoEscapeAnalysis -XX:+UseCodeCacheFlushing -XX:+UseFastJNIAccessors -XX:+OptimizeStringConcat -XX:+UseCompressedOops -XX:+UseThreadPriorities -XX:+OmitStackTraceInFastThrow -XX:+TrustFinalNonStaticFields -XX:ThreadPriorityPolicy=1 -XX:+UseInlineCaches -XX:+RewriteBytecodes -XX:+RewriteFrequentPairs -XX:+UseNUMA -XX:-DontCompileHugeMethods -XX:+UseCMoveUnconditionally -XX:+UseFPUForSpilling -XX:+UseNewLongLShift -XX:+UseVectorCmov -XX:+UseXMMForArrayCopy -XX:+UseXmmI2D -XX:+UseXmmI2F -XX:+UseXmmLoadAndClearUpper -XX:+UseXmmRegToRegMoveAll -Dgraal.TuneInlinerExploration=1 -Dgraal.CompilerConfiguration=enterprise -Dgraal.UsePriorityInlining=true -Dgraal.Vectorization=true -Dgraal.OptDuplication=true -Dgraal.DetectInvertedLoopsAsCounted=true -Dgraal.LoopInversion=true -Dgraal.VectorizeHashes=true -Dgraal.EnterprisePartialUnroll=true -Dgraal.VectorizeSIMD=true -Dgraal.StripMineNonCountedLoops=true -Dgraal.SpeculativeGuardMovement=true -Dgraal.InfeasiblePathCorrelation=true -DPlazma.disableConfigOptimization -Dfile.encoding=UTF-8 -Xlog:async -Djava.security.egd=file:/dev/urandom --add-modules=jdk.incubator.vector`***-jar server.jar***
> [!IMPORTANT]
> Ptedrodactyl Panel users must set the -Xmx and -Xms value to 70-80% of the server's RAM in order to cover the Java's Overhead memory
> Additionally, you can "automate" the value by setting this: 
> ```
> -Xms$(({{SERVER_MEMORY}} - ({{SERVER_MEMORY}}/20)))M -Xmx$(({{SERVER_MEMORY}} - ({{SERVER_MEMORY}}/20)))M
> ```
> As you can see, the number `20` I've set above indicates how much RAM after divided to 20, subsequently the Server's allocated RAM would minus that divided value and SHOULD be able to run well   
___

That should be good i think

___

# Source:
- https://github.com/Obydux/Minecraft-GraalVM-Flags
- https://github.com/brucethemoose/Minecraft-Performance-Flags-Benchmarks
- https://www.reddit.com/r/feedthebeast/comments/18hta1r/how_i_about_doubled_my_minecraft_performance/
- https://obydux.github.io/Minecraft-startup-flags/
- https://github.com/brucethemoose/Minecraft-Performance-Flags-Benchmarks
- https://github.com/etil2jz/etil-minecraft-flags
- https://docs.papermc.io/paper/1.18/aikars-flags
