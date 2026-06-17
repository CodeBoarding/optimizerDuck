```mermaid
graph LR
    Diagnostic_Reporting_Engine["Diagnostic & Reporting Engine"]
    System_Interop_Validation["System Interop Validation"]
    Integrity_Revert_Verification["Integrity & Revert Verification"]
    Workflow_Integration_Testing["Workflow & Integration Testing"]
    Integrity_Revert_Verification -- "provides validation for" --> Workflow_Integration_Testing
    Workflow_Integration_Testing -- "utilizes providers from" --> System_Interop_Validation
    Workflow_Integration_Testing -- "generates data for" --> Diagnostic_Reporting_Engine
    System_Interop_Validation -- "supplies metadata to" --> Diagnostic_Reporting_Engine
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Provides logging, formatting, and a comprehensive testing suite to ensure the stability of optimization and revert logic.

### Diagnostic & Reporting Engine
Provides the production-side logic for gathering system metadata and formatting complex, nested optimization logs for the user interface.


**Related Classes/Methods**:

- `App.xaml.ScopeBlockTextFormatter`:36-114
- `Services.SystemInfoServiceTests`:6-27



**Source Files:**

- [`optimizerDuck.Test/Services/SystemInfoServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/SystemInfoServiceTests.cs)
  - `Services.SystemInfoServiceTests.RefreshAsync_SetsSnapshot()` ([L9-L18](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/SystemInfoServiceTests.cs#L9-L18)) - Method
  - `Services.SystemInfoServiceTests.LogSummary_DoesNotThrow()` ([L20-L26](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/SystemInfoServiceTests.cs#L20-L26)) - Method
- [`optimizerDuck/App.xaml.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck/App.xaml.cs)
  - `App.xaml.ScopeBlockTextFormatter.Format(LogEvent logEvent, TextWriter output)` ([L38-L89](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck/App.xaml.cs#L38-L89)) - Method
  - `App.xaml.ScopeBlockTextFormatter.RenderWithoutQuotes(LogEvent logEvent)` ([L90-L113](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck/App.xaml.cs#L90-L113)) - Method


### System Interop Validation
Ensures the reliability of the low-level services that interact directly with the Windows Registry, Shell, and Service Control Manager.


**Related Classes/Methods**:

- `Services.OptimizationServices.RegistryServiceTests`:16-399
- `Services.OptimizationServices.ShellPolicyTests`:6-257
- `Services.RegistryWatcherTests`:13-219



**Source Files:**

- [`optimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs)
  - `Services.OptimizationServices.RegistryServiceTests.DummyOptimization` ([L21-L35](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L21-L35)) - Class
  - `Services.OptimizationServices.RegistryServiceTests.RegistryServiceTests()` ([L36-L44](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L36-L44)) - Constructor
  - `Services.OptimizationServices.RegistryServiceTests.Dispose()` ([L45-L50](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L45-L50)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.CleanupTestKey()` ([L51-L63](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L51-L63)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.Read_WithInvalidRoot_ReturnsDefault()` ([L65-L71](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L65-L71)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.DeleteValue_WithInvalidRoot_ReturnsFalse()` ([L73-L79](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L73-L79)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.Write_WithNullValue_ReturnsFalse()` ([L81-L87](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L81-L87)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.DeleteValue_RestorePreviousValue_OnRevert()` ([L89-L103](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L89-L103)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.DeleteDefaultValue_RestorePreviousValue_OnRevert()` ([L105-L119](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L105-L119)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.WriteDefaultValue_OverwriteValue_RevertRestoresPreviousValue()` ([L121-L137](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L121-L137)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.DeleteSubKeyTree_CreatesRecursiveBackupAndRestoresCorrectly()` ([L139-L191](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L139-L191)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.CreateSubKey_TracksCreatedKeysAndRemovesIfEmptyOnRevert()` ([L193-L215](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L193-L215)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.MultiStepRegistryOperation_PartialFailure_RollbackRestoresOriginalState()` ([L217-L257](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L217-L257)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.ConcurrentRegistryOperations_DoesNotCauseCorruption()` ([L259-L291](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L259-L291)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.RegistryValueKindConversion_HandlesAllTypesCorrectly()` ([L293-L334](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L293-L334)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.RevertStepWithSubSteps_ExecutesInCorrectOrder()` ([L336-L371](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L336-L371)) - Method
  - `Services.OptimizationServices.RegistryServiceTests.CleanupEmptyKeys_RemovesOnlyEmptyKeys()` ([L373-L398](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L373-L398)) - Method
- [`optimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs)
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_ExitCodeZero_ReturnsSuccess()` ([L9-L22](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L9-L22)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_NonZeroExitCode_ReturnsFailure()` ([L24-L37](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L24-L37)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_WithStderr_ReturnsStderrAsError()` ([L39-L53](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L39-L53)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_WithoutStderr_ReturnsExitCodeMessage()` ([L55-L69](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L55-L69)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_TimedOut_ReturnsTimeoutMessage()` ([L71-L85](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L71-L85)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.SuccessExitCodes_WithAllowedExitCode_ReturnsSuccess()` ([L87-L102](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L87-L102)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.SuccessExitCodes_WithDisallowedExitCode_ReturnsFailure()` ([L104-L119](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L104-L119)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.SuccessExitCodeRange_WithInRange_ReturnsSuccess()` ([L121-L136](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L121-L136)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.SuccessExitCodeRange_WithNegativeExitCode_ReturnsFailure()` ([L138-L153](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L138-L153)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.SuccessExitCodeRange_WithOutOfRange_ReturnsFailure()` ([L155-L170](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L155-L170)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.From_CustomPolicy_UsesCustomPredicate()` ([L172-L197](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L172-L197)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.From_WithCustomErrorFactory_UsesCustomFactory()` ([L199-L217](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L199-L217)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.From_WithoutErrorFactory_UsesDefault()` ([L219-L234](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L219-L234)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_IsSingleton()` ([L236-L240](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L236-L240)) - Method
  - `Services.OptimizationServices.ShellPolicyTests.DefaultPolicy_ExitCodeNegativeOne_AlwaysReturnsTimeoutMessage()` ([L242-L256](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L242-L256)) - Method
- [`optimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs)
  - `Services.OptimizationServices.ShellServiceTests.Cmd_ExitZero_ReturnsSuccessExitCode()` ([L8-L14](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs#L8-L14)) - Method
  - `Services.OptimizationServices.ShellServiceTests.Cmd_ExitOne_ReturnsNonZeroExitCode()` ([L16-L22](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs#L16-L22)) - Method
  - `Services.OptimizationServices.ShellServiceTests.PowerShell_SimpleCommand_ReturnsSuccessExitCode()` ([L24-L30](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs#L24-L30)) - Method
- [`optimizerDuck.Test/Services/RegistryWatcherTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs)
  - `Services.RegistryWatcherTests.RegistryWatcherTests()` ([L18-L22](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L18-L22)) - Constructor
  - `Services.RegistryWatcherTests.Dispose()` ([L23-L27](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L23-L27)) - Method
  - `Services.RegistryWatcherTests.Cleanup()` ([L28-L40](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L28-L40)) - Method
  - `Services.RegistryWatcherTests.Watch_And_Unwatch_DoesNotThrow()` ([L42-L52](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L42-L52)) - Method
  - `Services.RegistryWatcherTests.Watch_SamePathTwice_DoesNotDuplicate()` ([L54-L63](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L54-L63)) - Method
  - `Services.RegistryWatcherTests.Watch_EmptyPath_DoesNotThrow()` ([L65-L72](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L65-L72)) - Method
  - `Services.RegistryWatcherTests.RegistryChange_FiresEvent()` ([L74-L102](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L74-L102)) - Method
  - `Services.RegistryWatcherTests.RegistryChange_AfterUnwatch_DoesNotFire()` ([L104-L130](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L104-L130)) - Method
  - `Services.RegistryWatcherTests.MultipleWatchers_IndependentPaths_BothFire()` ([L132-L185](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L132-L185)) - Method
  - `Services.RegistryWatcherTests.Dispose_CleansUpAllWatchers()` ([L187-L198](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L187-L198)) - Method
  - `Services.RegistryWatcherTests.Dispose_MultipleCalls_DoesNotThrow()` ([L200-L209](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L200-L209)) - Method
  - `Services.RegistryWatcherTests.Watch_AfterDispose_ThrowsObjectDisposed()` ([L211-L218](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L211-L218)) - Method


### Integrity & Revert Verification
The core safety component that validates the serialization of system states and the end-to-end integrity of the rollback mechanism.


**Related Classes/Methods**:

- `Domain.Revert.Steps.RevertStepSerializationTests`:8-489
- `Services.ApplyRevertComprehensiveTests`:20-1134
- `Domain.Exceptions.StepExecutionExceptionTests`:5-43



**Source Files:**

- [`optimizerDuck.Test/Domain/Exceptions/StepExecutionExceptionTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Exceptions/StepExecutionExceptionTests.cs)
  - `Domain.Exceptions.StepExecutionExceptionTests.Constructor_WithErrorAndDetail_SetsProperties()` ([L8-L15](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Exceptions/StepExecutionExceptionTests.cs#L8-L15)) - Method
  - `Domain.Exceptions.StepExecutionExceptionTests.Constructor_WithNullError_UsesDefaultMessage()` ([L17-L24](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Exceptions/StepExecutionExceptionTests.cs#L17-L24)) - Method
  - `Domain.Exceptions.StepExecutionExceptionTests.Constructor_WithErrorOnly_SetsMessageAndNullDetail()` ([L26-L33](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Exceptions/StepExecutionExceptionTests.cs#L26-L33)) - Method
  - `Domain.Exceptions.StepExecutionExceptionTests.Constructor_WithDetailOnly_DefaultMessageUsed()` ([L35-L42](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Exceptions/StepExecutionExceptionTests.cs#L35-L42)) - Method
- [`optimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs)
  - `Domain.Revert.Steps.RevertStepSerializationTests.ShellRevertStep_RoundTrip_PreservesAllProperties()` ([L11-L26](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L11-L26)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ShellRevertStep_PowerShell_RoundTrip()` ([L28-L42](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L28-L42)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ShellRevertStep_WithEmptyCommand_RoundTrip()` ([L44-L53](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L44-L53)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ServiceRevertStep_RoundTrip_PreservesAllProperties()` ([L55-L70](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L55-L70)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ServiceRevertStep_Disabled_RoundTrip()` ([L72-L86](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L72-L86)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ServiceRevertStep_Manual_RoundTrip()` ([L88-L101](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L88-L101)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ServiceRevertStep_DelayedStart_RoundTrip()` ([L103-L116](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L103-L116)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ServiceRevertStep_EmptyServiceName_RoundTrip()` ([L118-L131](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L118-L131)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ScheduledTaskRevertStep_RoundTrip_PreservesAllProperties()` ([L133-L148](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L133-L148)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ScheduledTaskRevertStep_DisabledTask_RoundTrip()` ([L150-L163](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L150-L163)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.ScheduledTaskRevertStep_WithBothEnabledStates_RoundTrip(bool originalState)` ([L167-L180](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L167-L180)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.UsbPowerRevertStep_RoundTrip_PreservesAllProperties()` ([L182-L211](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L182-L211)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.UsbPowerRevertStep_EmptyStates_RoundTrip()` ([L213-L222](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L213-L222)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousDWord_RoundTrip()` ([L224-L244](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L224-L244)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousQWord_RoundTrip()` ([L246-L263](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L246-L263)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousString_RoundTrip()` ([L265-L281](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L265-L281)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousExpandString_RoundTrip()` ([L283-L300](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L283-L300)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousMultiString_RoundTrip()` ([L302-L320](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L302-L320)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousBinary_RoundTrip()` ([L322-L340](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L322-L340)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestorePreviousNullValue_RoundTrip()` ([L342-L358](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L342-L358)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_NoPreviousValue_RoundTrip()` ([L360-L376](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L360-L376)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_DefaultValueName_RoundTrip()` ([L378-L395](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L378-L395)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_RestoreKeyAction_RoundTrip()` ([L397-L411](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L397-L411)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_DeleteKeyAction_RoundTrip()` ([L413-L427](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L413-L427)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_WithCreatedSubKeys_RoundTrip()` ([L429-L452](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L429-L452)) - Method
  - `Domain.Revert.Steps.RevertStepSerializationTests.RegistryRevertStep_WithSubSteps_RoundTrip()` ([L454-L488](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/RevertStepSerializationTests.cs#L454-L488)) - Method
- [`optimizerDuck.Test/Domain/Revert/Steps/ScheduledTaskRevertStepTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/ScheduledTaskRevertStepTests.cs)
  - `Domain.Revert.Steps.ScheduledTaskRevertStepTests.ExecuteAsync_WithMissingTask_ThrowsStepExecutionException()` ([L9-L21](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Domain/Revert/Steps/ScheduledTaskRevertStepTests.cs#L9-L21)) - Method
- [`optimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs)
  - `Services.ApplyRevertComprehensiveTests` ([L20-L1134](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L20-L1134)) - Class
  - `Services.ApplyRevertComprehensiveTests.ApplyAsync_AllStepsSuccess_CompleteRevertDataSaved()` ([L25-L117](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L25-L117)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyAsync_FirstStepFails_PartialSuccessWithGapInRevertData()` ([L123-L186](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L123-L186)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyAsync_MiddleStepsFail_MultipleGapsInRevertData()` ([L188-L268](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L188-L268)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyAsync_AllStepsFail_NoRevertDataFileCreated()` ([L270-L307](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L270-L307)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_AllStepsSucceed_FileDeletedAndSuccessReturned()` ([L313-L384](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L313-L384)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_StepsExecutedInReverseOrder_LastStepFirst()` ([L386-L459](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L386-L459)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_WithNullStepsInData_SkipsNullStepsSuccessfully()` ([L461-L533](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L461-L533)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_LastStepFails_PartialFailureWithFileDeleted()` ([L539-L604](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L539-L604)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_AllStepsFail_FilePreservedForRetry()` ([L606-L667](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L606-L667)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_PartialFailure_RetryActionCanRecoverFailedSteps()` ([L669-L743](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L669-L743)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyThenRevert_FullWorkflow_SuccessfulRoundTrip()` ([L749-L801](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L749-L801)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyPartialThenRevert_PartialApplyFollowedByRevert()` ([L803-L860](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L803-L860)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyRetryThenRevert_CompleteWorkflowWithRetry()` ([L862-L972](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L862-L972)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_NoRevertDataFile_ReturnsFailure()` ([L978-L993](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L978-L993)) - Method
  - `Services.ApplyRevertComprehensiveTests.RevertAsync_CorruptJsonFile_ReturnsFailure()` ([L995-L1021](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L995-L1021)) - Method
  - `Services.ApplyRevertComprehensiveTests.ApplyAsync_WithException_HandlesGracefully()` ([L1023-L1055](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L1023-L1055)) - Method
  - `Services.ApplyRevertComprehensiveTests.CreateService()` ([L1060-L1080](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L1060-L1080)) - Method
  - `Services.ApplyRevertComprehensiveTests.GetRevertFilePath(Guid id)` ([L1081-L1085](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L1081-L1085)) - Method
  - `Services.ApplyRevertComprehensiveTests.RunInStaThreadAsync(Func<Task> action)` ([L1086-L1108](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L1086-L1108)) - Method
  - `Services.ApplyRevertComprehensiveTests.TestOptimization` ([L1109-L1131](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L1109-L1131)) - Class
  - `Services.ApplyRevertComprehensiveTests.TestOptimization.ApplyAsync(IProgress<ProcessingProgress> progress, OptimizationContext context)` ([L1123-L1130](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/ApplyRevertComprehensiveTests.cs#L1123-L1130)) - Method
- [`optimizerDuck.Test/Services/Managers/RevertManagerTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs)
  - `Services.Managers.RevertManagerTests` ([L14-L289](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L14-L289)) - Class
  - `Services.Managers.RevertManagerTests.IsAppliedAsync_And_GetRevertDataAsync_HandleMissingFile()` ([L17-L27](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L17-L27)) - Method
  - `Services.Managers.RevertManagerTests.GetRevertDataAsync_ReadsValidPayload()` ([L29-L60](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L29-L60)) - Method
  - `Services.Managers.RevertManagerTests.IsAppliedAsync_WithInvalidJson_ReturnsFalse()` ([L62-L83](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L62-L83)) - Method
  - `Services.Managers.RevertManagerTests.RevertAsync_WithInvalidJson_ReturnsFailure()` ([L85-L111](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L85-L111)) - Method
  - `Services.Managers.RevertManagerTests.RevertAsync_WithPartialStepFailures_ReturnsFailure_And_DeletesFile()` ([L113-L172](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L113-L172)) - Method
  - `Services.Managers.RevertManagerTests.RevertAsync_WithAllStepFailures_LeavesFileForAnotherAttempt()` ([L174-L224](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L174-L224)) - Method
  - `Services.Managers.RevertManagerTests.RevertAsync_WithPartialFailures_RetryActionSucceedsAfterRevertDataIsDeleted()` ([L226-L288](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L226-L288)) - Method
  - `Services.Managers.RevertManagerTests.MockOptimization` ([L290-L307](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L290-L307)) - Class
  - `Services.Managers.RevertManagerTests.MockOptimization.ApplyAsync(IProgress<ProcessingProgress> progress, OptimizationContext context)` ([L299-L306](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L299-L306)) - Method
  - `Services.Managers.RevertManagerTests.RetryableTestRevertStep` ([L308-L349](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L308-L349)) - Class
  - `Services.Managers.RevertManagerTests.RetryableTestRevertStep.ExecuteAsync()` ([L320-L330](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L320-L330)) - Method
  - `Services.Managers.RevertManagerTests.RetryableTestRevertStep.ToData()` ([L331-L339](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L331-L339)) - Method
  - `Services.Managers.RevertManagerTests.RetryableTestRevertStep.FromData(JToken data)` ([L340-L348](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/Managers/RevertManagerTests.cs#L340-L348)) - Method
- [`optimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs)
  - `Services.OptimizationServiceIntegrationTests` ([L21-L222](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L21-L222)) - Class
  - `Services.OptimizationServiceIntegrationTests.TestRevertStep.ExecuteAsync()` ([L84-L89](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L84-L89)) - Method
  - `Services.OptimizationServiceIntegrationTests.TestRevertStep.ToData()` ([L90-L94](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L90-L94)) - Method
- [`optimizerDuck.Test/Services/OptimizationServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs)
  - `Services.OptimizationServiceTests` ([L16-L619](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L16-L619)) - Class
  - `Services.OptimizationServiceTests.ApplyAsync_Success_PersistsRevertDataFile()` ([L19-L64](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L19-L64)) - Method
  - `Services.OptimizationServiceTests.ApplyAsync_FailureMessage_StillPersistsSuccessfulSteps()` ([L66-L107](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L66-L107)) - Method
  - `Services.OptimizationServiceTests.RevertAsync_WithValidRevertData_RemovesFile()` ([L109-L162](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L109-L162)) - Method
  - `Services.OptimizationServiceTests.RetryFailedStepsWithResultsAsync_WhenRetrySucceeds_ReturnsRevertStepForOriginalIndex()` ([L164-L199](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L164-L199)) - Method
  - `Services.OptimizationServiceTests.ApplyAsync_PartialSuccess_PersistsRevertStepsAtOriginalIndexes()` ([L201-L281](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L201-L281)) - Method
  - `Services.OptimizationServiceTests.UpsertRevertStepAtIndexAsync_AfterRetrySuccess_InsertsStepAtFailedIndexWithoutShiftingLaterSteps()` ([L283-L386](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L283-L386)) - Method
  - `Services.OptimizationServiceTests.UpsertRevertStepAtIndexAsync_AfterMultipleRetrySuccesses_PreservesOriginalOrder()` ([L388-L509](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L388-L509)) - Method
  - `Services.OptimizationServiceTests.RetryFailedStepsWithResultsAsync_WhenRetryStillFails_ReturnsUpdatedFailedStep()` ([L511-L537](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L511-L537)) - Method
  - `Services.OptimizationServiceTests.CreateService()` ([L538-L558](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L538-L558)) - Method
  - `Services.OptimizationServiceTests.GetRevertFilePath(Guid id)` ([L559-L563](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L559-L563)) - Method
  - `Services.OptimizationServiceTests.RunInStaThreadAsync(Func<Task> action)` ([L564-L586](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L564-L586)) - Method
  - `Services.OptimizationServiceTests.FakeOptimization` ([L587-L618](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L587-L618)) - Class
  - `Services.OptimizationServiceTests.FakeOptimization.ApplyAsync(IProgress<ProcessingProgress> progress, OptimizationContext context)` ([L610-L617](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceTests.cs#L610-L617)) - Method
- [`optimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs)
  - `Services.OptimizationServices.RegistryServiceTests` ([L16-L399](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L16-L399)) - Class
  - `Services.OptimizationServices.RegistryServiceTests.DummyOptimization.ApplyAsync(IProgress<ProcessingProgress> progress, OptimizationContext context)` ([L30-L34](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/RegistryServiceTests.cs#L30-L34)) - Method
- [`optimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs)
  - `Services.OptimizationServices.ShellPolicyTests` ([L6-L257](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellPolicyTests.cs#L6-L257)) - Class
- [`optimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs)
  - `Services.OptimizationServices.ShellServiceTests` ([L5-L31](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServices/ShellServiceTests.cs#L5-L31)) - Class
- [`optimizerDuck.Test/Services/RegistryWatcherTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs)
  - `Services.RegistryWatcherTests` ([L13-L219](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/RegistryWatcherTests.cs#L13-L219)) - Class
- [`optimizerDuck.Test/Services/SystemInfoServiceTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/SystemInfoServiceTests.cs)
  - `Services.SystemInfoServiceTests` ([L6-L27](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/SystemInfoServiceTests.cs#L6-L27)) - Class


### Workflow & Integration Testing
Manages the high-level validation of the optimization lifecycle, including execution context tracking and partial failure handling.


**Related Classes/Methods**:

- `Services.OptimizationExecutionContextTests.ExecutionScopeTests`:11-173
- `Services.OptimizationServiceIntegrationTests`:21-222



**Source Files:**

- [`optimizerDuck.Test/Services/OptimizationExecutionContextTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs)
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests` ([L11-L173](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L11-L173)) - Class
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.RecordStep_WithSuccessfulStep_RecordsStep()` ([L14-L26](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L14-L26)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.RecordStep_WithFailedStep_RecordsFailedStep()` ([L28-L41](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L28-L41)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.RecordStep_WithRevertStep_RecordsRevertData()` ([L43-L55](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L43-L55)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.FailedSteps_ReturnsOnlyFailedSteps()` ([L57-L72](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L57-L72)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.StepIndex_IncrementsSequentially()` ([L74-L88](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L74-L88)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.Dispose_ClearsCurrentScope()` ([L90-L105](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L90-L105)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.Begin_WithLogger_CreatesLightweightScope()` ([L107-L119](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L107-L119)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.Begin_ThrowsIfAlreadyActive()` ([L121-L131](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L121-L131)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.RecordStep_WithoutActiveScope_ReturnsNull()` ([L133-L139](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L133-L139)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.Track_UpdatesStats()` ([L141-L154](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L141-L154)) - Method
  - `Services.OptimizationExecutionContextTests.ExecutionScopeTests.GetStepResults_ReturnsOperationStepResults()` ([L156-L172](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L156-L172)) - Method
  - `Services.OptimizationExecutionContextTests.MockOptimization` ([L174-L191](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L174-L191)) - Class
  - `Services.OptimizationExecutionContextTests.MockOptimization.ApplyAsync(IProgress<ProcessingProgress> progress, OptimizationContext context)` ([L183-L190](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L183-L190)) - Method
  - `Services.OptimizationExecutionContextTests.MockRevertStep` ([L192-L212](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L192-L212)) - Class
  - `Services.OptimizationExecutionContextTests.MockRevertStep.ExecuteAsync()` ([L197-L201](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L197-L201)) - Method
  - `Services.OptimizationExecutionContextTests.MockRevertStep.ToData()` ([L202-L206](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L202-L206)) - Method
  - `Services.OptimizationExecutionContextTests.MockRevertStep.FromData(JObject data)` ([L207-L211](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationExecutionContextTests.cs#L207-L211)) - Method
- [`optimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs`](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs)
  - `Services.OptimizationServiceIntegrationTests.PartialFailureOptimization` ([L23-L77](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L23-L77)) - Class
  - `Services.OptimizationServiceIntegrationTests.PartialFailureOptimization.PartialFailureOptimization(bool shouldFail = false)` ([L35-L39](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L35-L39)) - Constructor
  - `Services.OptimizationServiceIntegrationTests.PartialFailureOptimization.ApplyAsync(IProgress<ProcessingProgress> progress, OptimizationContext context)` ([L40-L76](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L40-L76)) - Method
  - `Services.OptimizationServiceIntegrationTests.TestRevertStep` ([L78-L95](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L78-L95)) - Class
  - `Services.OptimizationServiceIntegrationTests.OptimizationServiceIntegrationTests()` ([L98-L99](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L98-L99)) - Constructor
  - `Services.OptimizationServiceIntegrationTests.Dispose()` ([L100-L117](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L100-L117)) - Method
  - `Services.OptimizationServiceIntegrationTests.ApplyAsync_WithSuccess_SavesRevertDataCorrectly()` ([L119-L148](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L119-L148)) - Method
  - `Services.OptimizationServiceIntegrationTests.UpdateOptimizationStateAsync_WithMissingData_HandlesGracefully()` ([L150-L165](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L150-L165)) - Method
  - `Services.OptimizationServiceIntegrationTests.RetryFailedStepsAsync_WithRetryableSteps_Succeeds()` ([L167-L193](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L167-L193)) - Method
  - `Services.OptimizationServiceIntegrationTests.RetryFailedStepsAsync_WithNonRetryableSteps_RemainsFailed()` ([L195-L221](https://github.com/CodeBoarding/optimizerDuck/blob/master/.codeboardingoptimizerDuck.Test/Services/OptimizationServiceIntegrationTests.cs#L195-L221)) - Method




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)