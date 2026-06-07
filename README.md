# NRM ontology

version: 1.0

ontology:
  name: NRM1
  release: 2021

group_elements:

  - code: "2"
    name: Superstructure

    description: >
      Structural and enclosing elements above substructure.

    elements:

      - code: "2.1"
        name: Frame

        description: >
          Structural framing systems.

        sub_elements:

          - code: "2.1.1"
            name: Steel Frames

            measurement:

              unit: m2

              quantity_type: area

              measurement_method: >
                Area of floors supported by frame.

              source_priority:
                - IFC
                - BIM
                - CAD
                - PDF
                - Specification

            classifications:

              nrm:
                code: "2.1.1"

              uniclass:
                - Ss_25

              ifc:
                - IfcBeam
                - IfcColumn
                - IfcMember

            extraction:

              keywords:
                - steel frame
                - structural steel
                - portal frame
                - universal beam
                - universal column

              drawing_patterns:
                - "S-*"
                - "GA-*"

              cad_layers:
                - STEEL
                - STRUCTURAL

              specification_patterns:
                - structural steelwork
                - steel framing system

            validation:

              minimum_quantity: 0

              acceptable_units:
                - m2

              geometry_required: true

            boq_templates:

              - template_code: BOQ-STEEL-FRAME-001

                name: Structural Steel Frame

                trade:
                  code: STR
                  name: Structural Steel

                measurement_unit: m2

                line_items:

                  - item_code: STR-001
                    description: Supply structural steel frame
                    quantity_source: measured_quantity

                  - item_code: STR-002
                    description: Fabrication of steel members
                    quantity_source: measured_quantity

                  - item_code: STR-003
                    description: Erection and installation
                    quantity_source: measured_quantity

                  - item_code: STR-004
                    description: Bolts, cleats and connections
                    quantity_source: derived

                  - item_code: STR-005
                    description: Surface treatment and protection
                    quantity_source: measured_quantity

            embeddings:

              title: Steel Frames

              chunk_text: >
                NRM Group Element 2 Superstructure,
                Element 2.1 Frame,
                Sub Element 2.1.1 Steel Frames.
                Measure using floor area supported by frame.

              searchable_terms:
                - steel frame
                - structural frame
                - steel beam
                - steel column


# BOQ Template Structure
boq_templates:

  - template_code: WALL-001

    trade:
      code: WALL

    applies_to:
      nrm_codes:
        - 2.3.1
        - 2.3.2

    lines:

      - code: WALL-001
        description: External wall construction

      - code: WALL-002
        description: Insulation

      - code: WALL-003
        description: Vapour barrier

      - code: WALL-004
        description: Finishes

# Derived quantity rules
derived_quantities:

  - code: STEEL_CONNECTIONS

    description: Bolted connections

    formula: >

      steel_tonnage * 0.08

    output_unit: nr
