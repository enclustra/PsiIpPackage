## 2.6.0
* Added Features
  * Added [`gui_parameter_set_hidden`](CommandRef.md?#gui_parameter_set_hidden) function to hide a parameter in the GUI

## 2.5.1
* Bugfixes
  * Remove internal `package` procedure because of name-clash with Vivado build-in function.
    * Since _package.tcl_ scripts only used the external [`package_ip`](CommandRef.md?#package_ip) procedure, backwards-compartibility is guaranteed.

## 2.5.0
* Added Features
  * Set customized taxonomy with [`set_taxonomy`](CommandRef.md?#set_taxonomy)
  * Configure constraints settings (used_in, processing_order, scoped_to_cells) with [`set_constrs_settings`](CommandRef.md?#set_constrs_settings)
  * Add Sub-Core References to Xilinx IP with [`add_sub_core_reference`](CommandRef.md?#add_sub_core_reference)
  * Add ToolTip to GUI parameters with [`gui_parameter_set_tooltip`](CommandRef.md?#gui_parameter_set_tooltip)
  * Add most common single-bit interfaces (clock, reset, interrupt)
    * See [`add_reset_in_interface`](CommandRef.md?#add_reset_in_interface)
    * See [`add_clock_out_interface`](CommandRef.md?#add_clock_out_interface)
    * See [`add_reset_out_interface`](CommandRef.md?#add_reset_out_interface)
    * See [`add_interrupt_out_interface`](CommandRef.md?#add_interrupt_out_interface)
* Changes
  * Allow to set FreqHz parameter for Clock-In interface with [`add_clock_in_interface`](CommandRef.md?#add_clock_in_interface)
  * Change [`add_bus_interface`](CommandRef.md?#add_bus_interface) to map bus interfaces with the **abstraction** name. This is necessary, since some interfaces have multiple abstractions.
  * Update baremetal-driver [Makefile](Snippets/driver/Makefile) snippet to be compartible with newer Vivado versions.

## 2.4.0
* Added Features
  * Automatically create driver directories
  * Generated Makefile Vivado compatible
  * Added Option to add parameter values to xparameters.h

## 2.3.0
* Added Features
  * GUI supports dropdown lists and pairs
  * Added function to import user interface definitions and map IP ports to a bus interface
  * Added support for multiple interfaces in functions [`remove_autodetected_interface`](CommandRef.md?#remove_autodetected_interface) and [`set_interface_clock`](CommandRef.md?#set_interface_clock)
  * Cleaned up device families
  * Added function to set target language
  * Added function [`add_reset_in_interface`](CommandRef.md?#add_reset_in_interface) similiar to [`add_clock_in_interface`](CommandRef.md?#add_clock_in_interface)
  * Added functions [`set_interface_mode`](CommandRef.md?#set_interface_mode), [`add_gui_support_tcl`](CommandRef.md?#add_gui_support_tcl) and [`gui_parameter_set_expression`](CommandRef.md?#gui_parameter_set_expression)
* Bugfixes
  * Fixed bug in packaging for [`add_lib_copied`](CommandRef.md?#add_lib_copied)
  * Prevent removed files from being added when it's still in sim sources

## 2.2.0
* Added Features
  * VHDL 2008 support by default
  * Added options to set vendor properties

## 2.1.0
* Added Features
  * Allow manual selection of the library to compile files into
* Bugfixes
  * Reorder actions to allow removing and re-adding clock interfaces (useful if vivado wrongly auto-detects associations of clocks to bus-interfaces)

## 2.0.0
* First Open Source Release (older versions not kept in history)
* Changes
  * Removed *has_std_axi_if* command (too PSI specific)
  * Added TCL utilities (*PsiUtilPath* and *PsiUtilString*) in this repo instead of a dependency to a separate TCL Utilities repo

## 1.6.0
* Added Features
  * Allow setting display name in gui_create_user_parameter
* Bugfixes
  * Change relative paths to not include "./" as required by 2019.1

## 1.5.0
* Added Features
  * Added *add\_interface\_enablement\_condition* command to enable/disable whole interfaces
* Bugfixes
  * Fixed pint message during compilation of drivers

## 1.4.1
* Added Features
  * None
* Bugfixes
  * Print propper error message for unreferenced files (led to silent crash before)
  * Fixed path calculations to also work on Linux and with AFS
  * Part number was not used in build, fixed this

## 1.4.0
* Added Features
  * Added selection of device for test synthesis
* Bugfixes
  * Added all currently known families to "supported families" (otherwise families in beta state such as MPSOC did not work)

## 1.3.0
* Added Features
  * Added the option to manually specify the top level entity
  * Added code to support Vivado 2017.4 (1.2.0 does not work for 2017.4)
* Bugfixes
  * None

## 1.2.0
* Added Features
  * Implemented the handling of software drivers
* Bugfixes
  * None

## 1.1.0
* Added Features
  * Implemeted the option to manually associate a clock with an interface (Vivado often fails to automatically detect these relationships)
* Bugfixes
  * None

## V1.01
* Added Features
  * Implemented support for copied library files (copied into IP-core instead of relative reference)
  * Implemented pure GUI parameter (parameter for GUI that does not map to a VHDL generic)
  * Implemented propper handling of TCL namespaces
* Bugfixes
  * None

## V1.00
* First release
