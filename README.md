# <u>ICRC Content Package</u>

This content package is mainly for testing, this content has been gotten from the ugandaemr metadata repository. Thanks in advance!

The contents of a typical Content Package are:
* **Configuration**
    * This folder holds [Initializer compatible configuration metadata]([url](https://github.com/mekomsolutions/openmrs-module-initializer/blob/main/README.md)) that make up the content package. For example, in the /config directory, this includes:
        * **Forms** (in /ampathforms)
        * **Concepts** (in [/ocl]([url](https://github.com/mekomsolutions/openmrs-module-initializer/blob/main/README.md#:~:text=Open%20Concept%20Lab%20(ZIP%20Files))), [/concepts]([url](https://github.com/mekomsolutions/openmrs-module-initializer/blob/main/readme/concepts.md)))
        * **Programmatic Metadata** such as:
            * Programs (in [/programs]([url](https://github.com/mekomsolutions/openmrs-module-initializer/blob/main/readme/prog.md)))
            * Encounter types (in [/encountertypes]([url](https://github.com/mekomsolutions/openmrs-module-initializer/blob/main/readme/et.md)))
            * Workflows (in [/programworkflows]([url](https://github.com/mekomsolutions/openmrs-module-initializer/blob/main/readme/prog.md)))
            * Identifiers and other metadata
* **content.properties File**
    * Contents: This file specifies the required ESMs and OMODs (frontend modules and backend modules) that make up the Content Package.
    * Importance:
        * The content.properties file is important because when Implementers add this Content Package to their distribution, the content.properties file will automatically be read and compared with their exitisting distro.properties file.
        * An automatic distro Build Helper Tool then fetches the content package's information and extracts the content into the Implementation's distro.properties file.
        * **Dependencies** are especially important here, as the Build Helper Tool will add any dependencies from the Content Package into an Implementation's distro.properties file.

Running Spotless
----------------
This project uses Spotless for code formatting. Spotless is embedded in the build process, so when you run `mvn clean package`, Spotless will automatically format your code according to the project's style guidelines.

If you want to run Spotless separately, you can use the following Maven commands:

To apply the formatting:

    mvn spotless:apply

This will automatically format your code according to the project's style guidelines. It's recommended to run this command before committing your changes.

To check if your code adheres to the style guidelines without making any changes, you can run:

    mvn spotless:check

If this command reports any violations, you can then run `mvn spotless:apply` to fix them.

Remember, in most cases, you don't need to run these commands separately as Spotless will run automatically during the build process with `mvn clean package`.

# Detailed Breakdown of the Content Package

Clinical content package for the UgandaEMR+ distribution, containing metadata for HIV/ART, TB, MCH, and other Uganda-specific health programs.

## Overview

This content package provides the clinical metadata required to run UgandaEMR+ on OpenMRS 3.x. It includes forms, concepts, encounter types, programs, and other configuration necessary for Uganda's health information system (HMIS) compliance.

## Package Contents

### Backend Configuration (`configuration/backend_configuration/`)

| Folder | Description |
|--------|-------------|
| `ampathforms/` | JSON forms for O3 form engine (HMIS-compliant forms) |
| `htmlforms/` | Legacy HTML forms |
| `encountertypes/` | Encounter type definitions |
| `programs/` | Program definitions (HIV, TB, MCH) |
| `programworkflows/` | Program workflow definitions |
| `programworkflowstates/` | Workflow state definitions |
| `concepts/` | Concept definitions and ICD-11 mappings |
| `personattributetypes/` | Person attribute types |
| `visittypes/` | Visit type definitions |
| `relationshiptypes/` | Relationship type definitions |
| `privileges/` | Role and privilege definitions |
| `locations/` | Location and location tag definitions |
| `addresshierarchy/` | Uganda address hierarchy (districts, subcounties, etc.) |
| `stockmanagement/` | Stock management configuration |
| `orderfrequencies/` | Order frequency definitions |
| `appointmentspecialities/` | Appointment configuration |

### Frontend Configuration (`configuration/frontend_configuration/`)

| File | Description |
|------|-------------|
| `config.json` | O3 frontend configuration including module settings, UI customization, and privilege-based access |

## Programs Supported

- **HIV/ART Program** - Comprehensive HIV care and treatment tracking
- **TB Program** - Tuberculosis treatment and monitoring
- **MCH Program** - Maternal and child health services
- **EID Program** - Early infant diagnosis
- **SMC Program** - Safe male circumcision
- **HTS Program** - HIV testing services

## Forms Included

The package includes HMIS-compliant forms:

- ART Card forms (Summary, Encounter, Health Education, Family Tracking)
- Viral Load forms (Request, Non-Suppressed Register)
- EID forms (Request, Clinical Chart)
- HTS forms (Client Card, Contact Tracing)
- TB forms (Client Card, Second Line Treatment)
- MCH forms (Antenatal, Maternity, Postnatal)
- And many more...

## Installation

### Using Maven

Add this content package to your distribution's `distro.properties`:

```properties
content.icrc=${icrc-content.version}
```

## Directory Structure

```
icrc/
├── pom.xml                 # Maven build configuration
├── assembly.xml            # Package assembly descriptor
├── content.properties      # Package metadata and dependencies
├── README.md
└── configuration/
    ├── backend_configuration/
    │   ├── ampathforms/
    │   ├── htmlforms/
    │   ├── encountertypes/
    │   ├── programs/
    │   ├── programworkflows/
    │   ├── programworkflowstates/
    │   ├── concepts/
    │   ├── personattributetypes/
    │   ├── visittypes/
    │   ├── relationshiptypes/
    │   ├── privileges/
    │   ├── locations/
    │   ├── addresshierarchy/
    │   ├── stockmanagement/
    │   ├── orderfrequencies/
    │   └── appointmentspecialities/
    └── frontend_configuration/
        └── config.json
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## Related Resources

- [OpenMRS Content Packages Documentation](https://openmrs.atlassian.net/wiki/spaces/docs/pages/183795733/OpenMRS+Content+Packages+Templates)
- [Initializer Module](https://github.com/mekomsolutions/openmrs-module-initializer)
- [UgandaEMR Documentation](https://ugandaemr.github.io/)


