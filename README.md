# Vibe-Navigation

## Schematic
![Vibe-Navigation Schematic.png](./assets/imgs/Vibe-Nevigation.png)

## Flowchart
```graph TD
subgraph Power_Supply_System
    B[2x 3.7V LiPo Batteries] --> C{Parallel Connection};
    C --> D[Total 3.7V / 4000mAh Output];
    D --> E[Step-down Converter (3.3V)];
end

subgraph User_Input_and_Sensing
    A1[Analog Joysticks] --> F1[ADC (Analog-to-Digital Converter)];
    A2[Analog Triggers] --> F2[ADC (Analog-to-Digital Converter)];
    A3[16 Digital Buttons] --> F3[GPIO Inputs];
    A4[MPU-6050] --> F4[I2C Communication];
end

subgraph Microcontroller_Core
    E --> G[ESP32-S3 Microcontroller];
    F1 --> G;
    F2 --> G;
    F3 --> G;
    F4 --> G;
end

subgraph Data_Processing_and_Output
    G --> H[Input Data Processing];
    H --> I[Wired Communication (USB-C)];
end

subgraph Physical_Connections
    J[USB-C Port] --> K[PC / Host Device];
end

E --> G;
G --> H;
H --> I;
I --> J;
J --> K;

style A1 fill:#f9f,stroke:#333,stroke-width:2px
style A2 fill:#f9f,stroke:#333,stroke-width:2px
style A3 fill:#f9f,stroke:#333,stroke-width:2px
style A4 fill:#f9f,stroke:#333,stroke-width:2px
style B fill:#9f9,stroke:#333,stroke-width:2px
style D fill:#9f9,stroke:#333,stroke-width:2px
style E fill:#9f9,stroke:#333,stroke-width:2px
style G fill:#ccf,stroke:#333,stroke-width:2px
style F1 fill:#ffc,stroke:#333,stroke-width:2px
style F2 fill:#ffc,stroke:#333,stroke-width:2px
style F3 fill:#ffc,stroke:#333,stroke-width:2px
style F4 fill:#ffc,stroke:#333,stroke-width:2px
style H fill:#fcc,stroke:#333,stroke-width:2px
style I fill:#fcc,stroke:#333,stroke-width:2px
style J fill:#fcc,stroke:#333,stroke-width:2px
style K fill:#fff,stroke:#333,stroke-width:2px
classDef mainNode stroke-width:3px;
class G,H,I mainNode;

linkStyle 0,1,2,3,4,5,6,7,8,9,10,11 stroke-width:2px,fill:none,stroke:green;
```
