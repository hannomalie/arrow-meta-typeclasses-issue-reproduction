 Playground for arrow meta compiler plugin stuff.
 Using type classes results in the following error when running 
 
 
 ./gradlew assemble

> Task :compileKotlin FAILED
e: java.lang.IndexOutOfBoundsException: Empty list doesn't contain element at index 0.
        at kotlin.collections.EmptyList.get(Collections.kt:34)
        at kotlin.collections.EmptyList.get(Collections.kt:22)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt.dataTypeDescriptor(TypeClassesPlugin.kt:209)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt.findExtension(TypeClassesPlugin.kt:98)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt.extensionCall(TypeClassesPlugin.kt:88)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt.mapValueParameterExtensions(TypeClassesPlugin.kt:84)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt.access$mapValueParameterExtensions(TypeClassesPlugin.kt:1)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt$typeClasses$1$3.invoke(TypeClassesPlugin.kt:64)
        at arrow.meta.plugins.typeclasses.TypeClassesPluginKt$typeClasses$1$3.invoke(TypeClassesPlugin.kt)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitFunctionAccess(IrSyntax.kt:454)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitFunctionAccess(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitCall(IrElementTransformer.kt:90)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitCall(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitCall(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.expressions.impl.IrCallImpl.accept(IrCallImpl.kt:89)
        at org.jetbrains.kotlin.ir.expressions.IrExpression$DefaultImpls.transform(IrExpression.kt:28)
        at org.jetbrains.kotlin.ir.expressions.impl.IrExpressionBase.transform(IrExpressionBase.kt:24)
        at org.jetbrains.kotlin.ir.declarations.impl.IrVariableImpl.transformChildren(IrVariableImpl.kt:93)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitDeclaration(IrElementTransformer.kt:38)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitDeclaration(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitDeclaration(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitVariable(IrElementTransformer.kt:49)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitVariable(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitVariable(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.declarations.impl.IrVariableImpl.accept(IrVariableImpl.kt:86)
        at org.jetbrains.kotlin.ir.declarations.IrDeclaration$DefaultImpls.transform(IrDeclaration.kt:42)
        at org.jetbrains.kotlin.ir.declarations.impl.IrDeclarationBase.transform(IrDeclarationBase.kt:27)
        at org.jetbrains.kotlin.ir.expressions.impl.IrBlockBodyImpl.transformChildren(IrBlockBodyImpl.kt:49)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitBody(IrElementTransformer.kt:55)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitBody(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitBody(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitBlockBody(IrElementTransformer.kt:58)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitBlockBody(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitBlockBody(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.expressions.impl.IrBlockBodyImpl.accept(IrBlockBodyImpl.kt:40)
        at org.jetbrains.kotlin.ir.expressions.IrBody$DefaultImpls.transform(IrBody.kt:24)
        at org.jetbrains.kotlin.ir.expressions.IrBlockBody$DefaultImpls.transform(IrBody.kt)
        at org.jetbrains.kotlin.ir.expressions.impl.IrBlockBodyImpl.transform(IrBlockBodyImpl.kt:26)
        at org.jetbrains.kotlin.ir.declarations.impl.IrFunctionBase.transformChildren(IrFunctionBase.kt:77)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitDeclaration(IrElementTransformer.kt:38)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitDeclaration(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitDeclaration(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitFunction(IrElementTransformer.kt:41)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitFunction(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitFunction(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.visitors.IrElementTransformer$DefaultImpls.visitSimpleFunction(IrElementTransformer.kt:42)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitSimpleFunction(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1$1.visitSimpleFunction(IrSyntax.kt:452)
        at org.jetbrains.kotlin.ir.declarations.impl.IrFunctionImpl.accept(IrFunctionImpl.kt:90)
        at org.jetbrains.kotlin.ir.declarations.IrDeclaration$DefaultImpls.transform(IrDeclaration.kt:42)
        at org.jetbrains.kotlin.ir.declarations.impl.IrDeclarationBase.transform(IrDeclarationBase.kt:27)
        at org.jetbrains.kotlin.ir.declarations.impl.IrFileImpl.transformChildren(IrFileImpl.kt:71)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1.invoke(IrSyntax.kt:452)
        at arrow.meta.dsl.codegen.ir.IrSyntax$irFunctionAccess$1.invoke(IrSyntax.kt:92)
        at arrow.meta.dsl.codegen.ir.IrSyntax$IrGeneration$1.generate(IrSyntax.kt:110)
        at arrow.meta.internal.registry.InternalRegistry$registerIRGeneration$1.generate(InternalRegistry.kt:297)
        at org.jetbrains.kotlin.backend.jvm.JvmBackendFacade.doGenerateFilesInternal$backend_jvm(JvmBackendFacade.kt:86)
        at org.jetbrains.kotlin.backend.jvm.JvmBackendFacade.doGenerateFilesInternal$backend_jvm$default(JvmBackendFacade.kt:64)
        at org.jetbrains.kotlin.backend.jvm.JvmBackendFacade.doGenerateFilesInternal$backend_jvm(JvmBackendFacade.kt:52)
        at org.jetbrains.kotlin.backend.jvm.JvmIrCodegenFactory.generateModule(JvmIrCodegenFactory.kt:36)
        at org.jetbrains.kotlin.codegen.KotlinCodegenFacade.doGenerateFiles(KotlinCodegenFacade.java:47)
        at org.jetbrains.kotlin.codegen.KotlinCodegenFacade.compileCorrectFiles(KotlinCodegenFacade.java:39)
        at org.jetbrains.kotlin.cli.jvm.compiler.KotlinToJVMBytecodeCompiler.generate(KotlinToJVMBytecodeCompiler.kt:637)
        at org.jetbrains.kotlin.cli.jvm.compiler.KotlinToJVMBytecodeCompiler.compileModules$cli(KotlinToJVMBytecodeCompiler.kt:195)
        at org.jetbrains.kotlin.cli.jvm.K2JVMCompiler.doExecute(K2JVMCompiler.kt:165)
        at org.jetbrains.kotlin.cli.jvm.K2JVMCompiler.doExecute(K2JVMCompiler.kt:55)
        at org.jetbrains.kotlin.cli.common.CLICompiler.execImpl(CLICompiler.kt:84)
        at org.jetbrains.kotlin.cli.common.CLICompiler.execImpl(CLICompiler.kt:42)
        at org.jetbrains.kotlin.cli.common.CLITool.exec(CLITool.kt:104)
        at org.jetbrains.kotlin.incremental.IncrementalJvmCompilerRunner.runCompiler(IncrementalJvmCompilerRunner.kt:349)
        at org.jetbrains.kotlin.incremental.IncrementalJvmCompilerRunner.runCompiler(IncrementalJvmCompilerRunner.kt:105)
        at org.jetbrains.kotlin.incremental.IncrementalCompilerRunner.compileIncrementally(IncrementalCompilerRunner.kt:237)
        at org.jetbrains.kotlin.incremental.IncrementalCompilerRunner.access$compileIncrementally(IncrementalCompilerRunner.kt:37)
        at org.jetbrains.kotlin.incremental.IncrementalCompilerRunner$compile$2.invoke(IncrementalCompilerRunner.kt:79)
        at org.jetbrains.kotlin.incremental.IncrementalCompilerRunner.compile(IncrementalCompilerRunner.kt:91)
        at org.jetbrains.kotlin.daemon.CompileServiceImplBase.execIncrementalCompiler(CompileServiceImpl.kt:606)
        at org.jetbrains.kotlin.daemon.CompileServiceImplBase.access$execIncrementalCompiler(CompileServiceImpl.kt:99)
        at org.jetbrains.kotlin.daemon.CompileServiceImpl.compile(CompileServiceImpl.kt:1645)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:498)
        at sun.rmi.server.UnicastServerRef.dispatch(UnicastServerRef.java:357)
        at sun.rmi.transport.Transport$1.run(Transport.java:200)
        at sun.rmi.transport.Transport$1.run(Transport.java:197)
        at java.security.AccessController.doPrivileged(Native Method)
        at sun.rmi.transport.Transport.serviceCall(Transport.java:196)
        at sun.rmi.transport.tcp.TCPTransport.handleMessages(TCPTransport.java:573)
        at sun.rmi.transport.tcp.TCPTransport$ConnectionHandler.run0(TCPTransport.java:834)
        at sun.rmi.transport.tcp.TCPTransport$ConnectionHandler.lambda$run$0(TCPTransport.java:688)
        at java.security.AccessController.doPrivileged(Native Method)
        at sun.rmi.transport.tcp.TCPTransport$ConnectionHandler.run(TCPTransport.java:687)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
        at java.lang.Thread.run(Thread.java:748)


FAILURE: Build failed with an exception.