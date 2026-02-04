# KiCad / SPICE Lab

## Git Repository Management

- `Fork` this repository.

- Add Dr. Palmeri (`mlp6`) as a Maintainer of your fork of the repository.

- `Clone` your forked repository to your local machine.

*Once you add Dr. Palmeri as a Maintainer, he will run a script behind the
scenes that will configure some settings on your repository.*

All of the `git` operations in this lab will be done on the `main` branch of
your forked repository.

## KiCad Schematic

- Open the `voltage-divider.kicad_pro` in KiCad.

- Populate the schematic footer with metadata.

- Create a `+9 V` net connected to a battery voltage source.

- Use `PWR_FLAG` components to indicate power source connections.

- Create a voltage divider circuit with two resistors (`R1` and `R2`) that will
generate 5 V from a 9 V source.  Choose resistor values such that the maximum
current sourced from the battery does not exceed 100 mA.

- Create a net label for the 5 V net called `Vin`.

- Use the net highlighter tool to verify that the `+9 V` and `GND` nets are
appropriately connected.

- Run the Electrical Rules Checker (ERC) and resolve any errors or warnings.

- Save your schematic.  The create a Git commit with a commit message indicating
that the schematic is passing the ERC.

- Push your updated local git repository commits to the remote repository.

## SPICE Simulation

### Operating Point

- Run an `Operating Point` SPICE simulation of your voltage divider circuit to verify that:

  - The voltage at the `Vin` net is 5 V.

  - The current sourced from the battery does not exceed 100 mA.

- Capture a screenshot of this simulation results window (either in the
simulator window or the results annotated on the circuit by the simulator).
Save this screenshot in a file called `spice-operating-point.png`.

- Create a Git commit with the saved SPICE simulation workbook and this
screenshot.

### "DC" Sweep

- Run a `DC Sweep` SPICE simulation of your voltage divider circuit while
sweeping the values of `R2` from the original value of `R2/2` to `2*R2`.

  - Plot the voltage at the `Vin` net as a function of the swept range of `R2` values.

  - Plot the current sourced from the battery as a function of the swept range of `R2` values.

  - Save a PNG of this these simulated outputs (on the same plot) in a file
  called `spice-dc-r2-sweep.png`.

- Create a Git commit with the saved updated SPICE simulation workbook (now with
two simulations configured) and this new screenshot.

- Push your updated local git repository commits to the remote repository.

### Submit via GitLab Issue

- Create an annotated tag (locally) of your latest commit called `v1.0.0`.

- Push this tag to your remote repository using the command `git push --tags`.

- On GitLab, create an Issue in your forked repository:

  - Title the Issue: `KiCad SPICE Simulations Complete`
  
  - Assign the Label `Review`.
  
  - Make Dr. Palmeri (`mlp6`) the Assignee.

## PCB Layout

*This will be a separate lab exercise.*

- Create a PCB layout for your voltage divider circuit, modifying it to use a
3-terminal potentiometer to be able to vary the output voltage `Vin` between 0 V
and 9 V.

- Make sure the populate the footer of the PCB layout with metadata.

- Your PCB should meeting the following specifications:

  - Single-sided board using thru-hole components.  *Remember, traces on the
  opposite side of the components!*

  - Your board edges should be a rectangle measuring 50 mm x 50 mm.

  - A ground plane in all non-component areas on the copper side of the PCB.

  - The footprint for your potentiometer should be
  `Potentiometer_THT:Potentiometer_Alpha_RD901F-40-00D_Single_Vertical`.

  - Your 9 V battery will not be mounted directly to the PCB, but will be
  connected via a 2-wire cable harness that will attach to a 1x2
  `Connector_THT:Conn_01x02_Male` header on the PCB.  Use footprint
  `B02B-XASK-1` for this connector.

  - `Vin` and `GND` should be available to connect to an external circuit via a
  1x2 `Connector_THT:Conn_01x02_Male` header on the PCB that also uses footprint
  `B02B-XASK-1`.

  - Add 4 mounting holes using the `MountingHole:MountingHole_M3` footprint in
  the corners of your PCB.

- Confirm that your Design Rules Check (DRC) passes with no errors or warnings.

- Create a Git commit with your updated schematic and PCB layout files.

- Create an annotated tag (locally) of your latest commit called `v2.0.0`.

- Push your new commits and tag to your remote repository.  *Remember, you have
to push the commits and the tags with separate commands.*

- On GitLab, create a new Issue in your forked repository:

  - Title the Issue: `KiCad PCB Layout Complete`
  
  - Assign the Label `Review`.
  
  - Make Dr. Palmeri (`mlp6`) the Assignee.
