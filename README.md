# neurodamus-models

This repository contains the technical mechanism files shared by the Open Brain Institute (OBI) simulators, [Neurodamus](https://github.com/openbraininstitute/neurodamus) and [BlueCelluLab](https://github.com/openbraininstitute/BlueCelluLab/). Scientific models are required to be supplied with circuit data. Together, the scientific models and the mechanism files provided by both this repository and an OBI simulator (Neurodamus or BlueCelluLab) enable in silico simulations through the NEURON simulator. The [SONATA specifications](https://sonata-extension.readthedocs.io/en/latest/mod_files.html) provide more details about supported mechanisms.

For the last release where all simulation models (neocortex, hippocampus, thalamus, and mousify) were bundled in a single repository, please refer to release 2.4.4.

## Installation

### Prerequisites

The [NEURON simulator](https://github.com/neuronsimulator/nrn) simulation framework can be
installed via pip:
```console
python -m pip install NEURON
````

### Compiling the models

```console
nrnivmodl -coreneuron <mod>
```

### Testing the models

Following the above step, the compiled mechanisms can be accessed from within NEURON,
e.g., with:
```console
./x86_64/special -python -c "from neuron import h; assert all(hasattr(h, attr) for attr in ['ConductanceSource', 'MembraneCurrentSource', 'InhPoissonStim', 'TTXDynamicsSwitch', 'VecStim']); h.quit()"
```

For an example on how to run a model with compiled mechanisms on a circuit, see the
[integration test of
Neurodamus](https://github.com/openbraininstitute/neurodamus/blob/main/.github/workflows/simulation_test.yml).

## Acknowledgements

The development of this software was supported by funding to the Blue Brain Project, a
research center of the École polytechnique fédérale de Lausanne (EPFL), from the Swiss
government’s ETH Board of the Swiss Federal Institutes of Technology.

Copyright (c) 2009-2024 Blue Brain Project/EPFL

Copyright (c) 2025 Open Brain Institute
