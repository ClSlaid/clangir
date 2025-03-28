set(
  LLVM_LINK_COMPONENTS
  Core
  Support
)

get_property(dialect_libs GLOBAL PROPERTY MLIR_DIALECT_LIBS)

add_clang_library(clangCIR
  CIRAsm.cpp
  CIRGenBuiltin.cpp
  CIRGenCXX.cpp
  CIRGenCXXABI.cpp
  CIRGenCall.cpp
  CIRGenClass.cpp
  CIRGenCleanup.cpp
  CIRGenCoroutine.cpp
  CIRGenDecl.cpp
  CIRGenDeclCXX.cpp
  CIRGenException.cpp
  CIRGenExpr.cpp
  CIRGenExprConst.cpp
  CIRGenExprAgg.cpp
  CIRGenExprCXX.cpp
  CIRGenExprScalar.cpp
  CIRGenFunction.cpp
  CIRGenItaniumCXXABI.cpp
  CIRGenModule.cpp
  CIRGenStmt.cpp
  CIRGenTBAA.cpp
  CIRGenTypes.cpp
  CIRGenVTables.cpp
  CIRGenerator.cpp
  CIRPasses.cpp
  CIRRecordLayoutBuilder.cpp
  ConstantInitBuilder.cpp
  TargetInfo.cpp

  DEPENDS
  MLIRCIR
  MLIRCIROpsIncGen
  MLIRCIRASTAttrInterfacesIncGen
  MLIRCIROpInterfacesIncGen
  ${dialect_libs}

  LINK_LIBS
  clangAST
  clangBasic
  clangLex
  ${dialect_libs}
  MLIRCIR
  MLIRCIRTransforms
  MLIRCIRInterfaces
  MLIRAffineToStandard
  MLIRAnalysis
  MLIRDLTIDialect
  MLIRFuncToLLVM
  MLIRIR
  MLIRLLVMCommonConversion
  MLIRLLVMDialect
  MLIRLLVMToLLVMIRTranslation
  MLIRMemRefDialect
  MLIRMemRefToLLVM
  MLIRParser
  MLIRPass
  MLIRSCFToControlFlow
  MLIRSideEffectInterfaces
  MLIRSupport
  MLIRTargetLLVMIRImport
  MLIRTargetLLVMIRExport
  MLIRTransforms
)
