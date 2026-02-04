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
