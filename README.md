# SiliconWit 2D Mechanisms Analyzer

![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)
![Version](https://img.shields.io/badge/version-1.0.0-green.svg)
![Browser](https://img.shields.io/badge/browser-compatible-orange.svg)

A comprehensive **Planar Mechanics Experimentation Tool** designed for Mechatronics Engineering Students. This interactive web application provides real-time visualization, kinematic analysis, and experimental data generation for fundamental mechanical linkages and mechanisms.

## 🎯 Purpose and Educational Goals

### **What This System Does**
- **Interactive Visualization**: Real-time animation of mechanical linkages with adjustable parameters
- **Kinematic Analysis**: Calculate and display position, velocity, and acceleration data
- **Experimental Design**: Run controlled experiments to understand mechanism behavior
- **Data Export**: Generate CSV data, CAD code, lab reports, and design specifications
- **Educational Resources**: Integrated learning materials and external resource links

### **Target Audience**
- **Mechatronics Engineering Students**: Learning planar kinematics and mechanism design
- **Mechanical Engineering Students**: Understanding linkage analysis and synthesis
- **Educators**: Teaching kinematic principles with interactive demonstrations
- **Researchers**: Rapid prototyping and validation of mechanism concepts
- **Industry Professionals**: Quick analysis and visualization of linkage systems

### **Learning Outcomes**
Students will be able to:
1. **Visualize** complex kinematic relationships in real-time
2. **Analyze** position, velocity, and acceleration characteristics
3. **Design** mechanisms using Grashof criteria and geometric constraints
4. **Experiment** with parameter variations and observe their effects
5. **Generate** professional documentation and CAD models
6. **Apply** theoretical knowledge to practical mechanism problems

## 🏗️ System Architecture

### **Core Design Philosophy**
- **Zero Dependencies**: Pure HTML/CSS/JavaScript with no external frameworks
- **Single File Deployment**: Entire application in one HTML file for maximum portability
- **Modular Extensibility**: Easy to add new mechanisms, experiments, and features
- **Educational Focus**: Optimized for learning rather than production complexity

### **Architecture Overview**
```
┌─────────────────────────────────────────────────────────────┐
│                    HTML5 Canvas Application                  │
├─────────────────────────────────────────────────────────────┤
│  Configuration Layer (mechanisms object)                    │
│  ├── Mechanism Definitions                                  │
│  ├── Parameter Specifications                               │
│  ├── Experiment Configurations                              │
│  └── Educational Content                                    │
├─────────────────────────────────────────────────────────────┤
│  User Interface Layer                                       │
│  ├── Dynamic HTML Generation                                │
│  ├── Responsive CSS Layout                                  │
│  ├── Event Handling System                                  │
│  └── Collapsible Results Interface                          │
├─────────────────────────────────────────────────────────────┤
│  Visualization Engine                                       │
│  ├── Canvas Drawing System                                  │
│  ├── Animation Control                                      │
│  ├── Coordinate Transformations                             │
│  └── Professional Graphics Rendering                        │
├─────────────────────────────────────────────────────────────┤
│  Kinematic Analysis Engine                                  │
│  ├── Position Analysis                                      │
│  ├── Velocity Calculations                                  │
│  ├── Acceleration Analysis                                  │
│  └── Geometric Constraint Solving                           │
├─────────────────────────────────────────────────────────────┤
│  Experiment System                                          │
│  ├── Data Collection                                        │
│  ├── Statistical Analysis                                   │
│  ├── Graph Generation                                       │
│  └── Results Visualization                                  │
├─────────────────────────────────────────────────────────────┤
│  Export System                                              │
│  ├── CSV Data Export                                        │
│  ├── FreeCAD Python Code Generation                         │
│  ├── Lab Report Templates                                   │
│  └── Design Specification Documents                         │
└─────────────────────────────────────────────────────────────┘
```

## 🚀 Quick Start Guide

### **For End Users**
1. **Download** the HTML file
2. **Open** in any modern web browser (Chrome, Firefox, Safari, Edge)
3. **Select** a mechanism from the dropdown
4. **Adjust** parameters using sliders
5. **Start** animation to observe motion
6. **Run** experiments to collect data
7. **Download** resources for further analysis

### **For Developers**
1. **Clone** or download the repository
2. **Open** the HTML file in your preferred code editor
3. **Study** the existing mechanism implementations
4. **Follow** the development patterns described below
5. **Test** changes by opening the file in a browser
6. **Contribute** improvements via pull requests

## 🛠️ Development Guide

### **Project Structure**
```
├── index.html                    # Main application file
│   ├── <style>                   # CSS styling and layout
│   ├── <body>                    # HTML structure
│   └── <script>                  # JavaScript application logic
│       ├── Global Variables      # State management
│       ├── Mechanism Definitions # Configuration objects
│       ├── UI Functions         # Interface management
│       ├── Drawing Engine       # Canvas rendering
│       ├── Animation System     # Real-time updates
│       ├── Experiment Engine    # Data collection
│       └── Export Functions     # File generation
└── README.md                     # This documentation
```

### **Key Design Patterns**

#### **1. Configuration-Driven Development**
All mechanisms are defined as data objects, making expansion straightforward:

```javascript
const mechanisms = {
    mechanismId: {
        name: "Display Name",
        description: "Brief description for UI",
        experiments: [...],      // Available experiments
        parameters: {...},       // Adjustable parameters
        info: [...]             // Educational content
    }
};
```

#### **2. Functional Decomposition**
Each major feature is broken into focused functions:
- `draw*()` functions handle visualization
- `run*Experiment()` functions collect data
- `generate*()` functions create exports
- `update*()` functions manage UI state

#### **3. Event-Driven Architecture**
User interactions trigger specific handlers:
- Parameter changes → immediate redraw
- Animation controls → start/stop loops
- Experiment selection → data collection
- Download buttons → file generation

## 📋 Adding New Mechanisms

### **Step 1: Define Mechanism Configuration**

Add your mechanism to the `mechanisms` object:

```javascript
const mechanisms = {
    // ... existing mechanisms
    
    yourmechanism: {
        name: "Your Mechanism Name",
        description: "What your mechanism does",
        experiments: [
            { 
                id: 'position-analysis', 
                name: 'Position Analysis', 
                desc: 'Study position characteristics' 
            },
            { 
                id: 'velocity-study', 
                name: 'Velocity Study', 
                desc: 'Analyze velocity profiles' 
            }
        ],
        parameters: {
            length1: { 
                name: 'First Link Length (mm)', 
                value: 100, 
                min: 50, 
                max: 200 
            },
            length2: { 
                name: 'Second Link Length (mm)', 
                value: 80, 
                min: 40, 
                max: 150 
            },
            angle_offset: { 
                name: 'Angular Offset (°)', 
                value: 0, 
                min: -90, 
                max: 90 
            }
        },
        info: [
            "First key characteristic of your mechanism",
            "Second important property",
            "Real-world applications: examples here",
            "Mathematical relationships: describe key equations",
            "Read more: <a href='https://siliconwit.com/education/planar-mechanics/' target='_blank' class='read-more-link'>siliconwit.com/education/planar-mechanics/</a> | Edit/contribute: <a href='https://github.com/SiliconWit/2d-mechanisms-analyzer' target='_blank' class='read-more-link'>GitHub</a>"
        ]
    }
};
```

### **Step 2: Add to UI Dropdown**

Update the HTML dropdown menu:

```html
<select class="mechanism-dropdown" id="mechanism-selector">
    <!-- existing options -->
    <option value="yourmechanism">Your Mechanism Name</option>
</select>
```

### **Step 3: Implement Drawing Function**

Create a drawing function following established patterns:

```javascript
function drawYourMechanism() {
    const params = mechanisms.yourmechanism.parameters;
    const L1 = params.length1.value;
    const L2 = params.length2.value;
    const offset = params.angle_offset.value * Math.PI / 180;

    // Calculate positions based on current angle and parameters
    const A = [0, 0];  // Fixed point
    const B = [L1 * Math.cos(angle + offset), L1 * Math.sin(angle + offset)];
    const C = [B[0] + L2 * Math.cos(angle * 2), B[1] + L2 * Math.sin(angle * 2)];

    // Draw mechanism components using helper functions
    drawLink(A, B, '#FF6B6B', 4);           // First link in red
    drawLink(B, C, '#4ECDC4', 4);           // Second link in teal
    
    // Draw joints
    drawJoint(A[0], A[1], '#333', true);    // Fixed joint
    drawJoint(B[0], B[1], '#FF6B6B');       // Moving joint
    drawJoint(C[0], C[1], '#4ECDC4');       // End effector

    // Add labels for clarity
    drawLabel("A", A[0], A[1], -15, -15);
    drawLabel("B", B[0], B[1], 15, 15);
    drawLabel("C", C[0], C[1], 15, -15);

    // Optional: Draw additional elements
    // drawGroundSymbol(A[0], A[1]);         // Ground symbol
    // drawTrajectory(C);                    // Path tracing
}
```

### **Step 4: Add to Drawing Switch**

Include your mechanism in the main drawing switch:

```javascript
function drawMechanism() {
    // ... existing code
    
    switch(currentMechanism) {
        case 'fourbar':
            drawFourBarLinkage();
            break;
        case 'slidercrank':
            drawSliderCrank();
            break;
        // ... other cases
        case 'yourmechanism':
            drawYourMechanism();
            break;
    }
    
    // ... rest of function
}
```

### **Step 5: Implement Experiments**

Create experiment functions for your mechanism:

```javascript
function runPositionAnalysis() {
    const params = mechanisms.yourmechanism.parameters;
    const L1 = params.length1.value;
    const L2 = params.length2.value;
    
    experimentData = []; // Clear previous data
    
    // Collect data over full rotation
    for (let theta = 0; theta <= 360; theta += 5) {
        const radians = theta * Math.PI / 180;
        
        // Calculate positions
        const B_x = L1 * Math.cos(radians);
        const B_y = L1 * Math.sin(radians);
        const C_x = B_x + L2 * Math.cos(radians * 2);
        const C_y = B_y + L2 * Math.sin(radians * 2);
        
        // Calculate derived quantities
        const distance_AC = Math.sqrt(C_x * C_x + C_y * C_y);
        const angle_AC = Math.atan2(C_y, C_x) * 180 / Math.PI;
        
        experimentData.push({
            input_angle: theta,
            position_B_x: B_x.toFixed(2),
            position_B_y: B_y.toFixed(2),
            position_C_x: C_x.toFixed(2),
            position_C_y: C_y.toFixed(2),
            distance_AC: distance_AC.toFixed(2),
            angle_AC: angle_AC.toFixed(1)
        });
    }
    
    updateResultsTable([
        'Input Angle (°)', 
        'B_x (mm)', 
        'B_y (mm)', 
        'C_x (mm)', 
        'C_y (mm)', 
        'Distance AC (mm)', 
        'Angle AC (°)'
    ]);
}

function runVelocityStudy() {
    const params = mechanisms.yourmechanism.parameters;
    const omega = 1; // rad/s input velocity
    
    experimentData = [];
    
    for (let theta = 0; theta <= 360; theta += 10) {
        const radians = theta * Math.PI / 180;
        
        // Velocity analysis using differentiation
        const vB_x = -L1 * omega * Math.sin(radians);
        const vB_y = L1 * omega * Math.cos(radians);
        const vC_x = vB_x - 2 * L2 * omega * Math.sin(radians * 2);
        const vC_y = vB_y + 2 * L2 * omega * Math.cos(radians * 2);
        
        const vB_magnitude = Math.sqrt(vB_x * vB_x + vB_y * vB_y);
        const vC_magnitude = Math.sqrt(vC_x * vC_x + vC_y * vC_y);
        
        experimentData.push({
            angle: theta,
            vB_x: vB_x.toFixed(3),
            vB_y: vB_y.toFixed(3),
            vB_mag: vB_magnitude.toFixed(3),
            vC_x: vC_x.toFixed(3),
            vC_y: vC_y.toFixed(3),
            vC_mag: vC_magnitude.toFixed(3)
        });
    }
    
    updateResultsTable([
        'Angle (°)', 
        'vB_x (mm/s)', 
        'vB_y (mm/s)', 
        '|vB| (mm/s)',
        'vC_x (mm/s)', 
        'vC_y (mm/s)', 
        '|vC| (mm/s)'
    ]);
}
```

### **Step 6: Add Experiments to Switch**

Include your experiments in the experiment handler:

```javascript
function runExperiment() {
    // ... existing code
    
    switch(currentExperiment) {
        // ... existing cases
        case 'position-analysis':
            runPositionAnalysis();
            break;
        case 'velocity-study':
            runVelocityStudy();
            break;
        default:
            runGenericExperiment();
    }
    
    plotResults();
}
```

## 🧪 Experiment Development

### **Experiment Design Principles**

1. **Educational Value**: Each experiment should teach a specific concept
2. **Progressive Complexity**: Start simple, build understanding gradually
3. **Visual Feedback**: Include graphical representation of results
4. **Quantitative Analysis**: Provide numerical data for further study
5. **Real-World Relevance**: Connect to practical applications

### **Experiment Function Template**

```javascript
function runYourExperiment() {
    const params = mechanisms[currentMechanism].parameters;
    
    // Extract parameters
    const param1 = params.parameter1.value;
    const param2 = params.parameter2.value;
    
    // Initialize data collection
    experimentData = [];
    
    // Data collection loop
    for (let i = 0; i <= steps; i += increment) {
        // Perform calculations
        const variable = calculateSomething(i, param1, param2);
        const derived = derivedCalculation(variable);
        
        // Store results
        experimentData.push({
            independent_var: i,
            dependent_var1: variable.toFixed(precision),
            dependent_var2: derived.toFixed(precision),
            // ... additional variables
        });
    }
    
    // Update display
    updateResultsTable(['Headers', 'For', 'Your', 'Data', 'Columns']);
}
```

### **Advanced Experiment Features**

#### **Parameter Sensitivity Analysis**
```javascript
function runParameterSensitivity() {
    const baseParams = mechanisms[currentMechanism].parameters;
    experimentData = [];
    
    // Vary one parameter while keeping others constant
    for (let variation = -20; variation <= 20; variation += 5) {
        const modifiedValue = baseParams.target_param.value * (1 + variation/100);
        
        // Run analysis with modified parameter
        const result = performAnalysis(modifiedValue);
        
        experimentData.push({
            variation_percent: variation,
            parameter_value: modifiedValue.toFixed(2),
            output_metric: result.toFixed(3)
        });
    }
    
    updateResultsTable(['Variation (%)', 'Parameter Value', 'Output Metric']);
}
```

#### **Optimization Studies**
```javascript
function runOptimization() {
    const params = mechanisms[currentMechanism].parameters;
    let bestValue = 0;
    let bestParams = {};
    
    experimentData = [];
    
    // Grid search over parameter space
    for (let p1 = params.param1.min; p1 <= params.param1.max; p1 += step1) {
        for (let p2 = params.param2.min; p2 <= params.param2.max; p2 += step2) {
            const objectiveValue = calculateObjective(p1, p2);
            
            if (objectiveValue > bestValue) {
                bestValue = objectiveValue;
                bestParams = {param1: p1, param2: p2};
            }
            
            experimentData.push({
                param1: p1,
                param2: p2,
                objective: objectiveValue.toFixed(4),
                is_best: objectiveValue === bestValue ? 'Yes' : 'No'
            });
        }
    }
    
    updateResultsTable(['Param1', 'Param2', 'Objective', 'Best?']);
}
```

## 📊 Data Export System

### **CSV Export Enhancement**

```javascript
function generateAdvancedCSV() {
    if (experimentData.length === 0) {
        alert('Please run an experiment first!');
        return;
    }
    
    const headers = Object.keys(experimentData[0]);
    const metadata = [
        `# SiliconWit 2D Mechanisms Analyzer Export`,
        `# Mechanism: ${mechanisms[currentMechanism].name}`,
        `# Experiment: ${currentExperiment}`,
        `# Date: ${new Date().toISOString()}`,
        `# Parameters: ${JSON.stringify(mechanisms[currentMechanism].parameters)}`,
        `#`,
        headers.join(',')
    ];
    
    const csvContent = [
        ...metadata,
        ...experimentData.map(row => 
            headers.map(header => row[header]).join(',')
        )
    ].join('\n');
    
    downloadFile(
        csvContent, 
        `${currentMechanism}_${currentExperiment}_${new Date().toISOString().slice(0,10)}.csv`, 
        'text/csv'
    );
}
```

### **Enhanced CAD Code Generation**

```javascript
function generateAdvancedCAD(mechanismType, params) {
    const mechanism = mechanisms[mechanismType];
    
    return `# FreeCAD Python Script for ${mechanism.name}
# Generated by SiliconWit.COM 2D Mechanisms Analyzer
# Date: ${new Date().toISOString()}
# Educational Resource: https://siliconwit.com/education/planar-mechanics/

import FreeCAD as App
import Part
import Sketcher
import Draft

# Create new document
doc = App.newDocument("${mechanismType}_mechanism")

# Mechanism Description
"""
${mechanism.description}

Key Characteristics:
${mechanism.info.slice(0, -1).map(info => `- ${info}`).join('\n')}
"""

# Parameters (in mm)
${Object.entries(params).map(([key, param]) => {
    return `${key} = ${param.value}  # ${param.name} (range: ${param.min}-${param.max})`;
}).join('\n')}

# Material Properties
material_density = 7850  # kg/m³ (steel)
material_yield = 250e6   # Pa (mild steel)
safety_factor = 2.0

# Manufacturing tolerances
standard_tolerance = 0.1  # mm
bearing_tolerance = 0.05  # mm

def create_link(name, length, width=10, thickness=5):
    """
    Create a standardized link with proper geometry and constraints
    
    Args:
        name (str): Component name
        length (float): Link length in mm
        width (float): Link width in mm
        thickness (float): Link thickness in mm
    
    Returns:
        Part.Feature: Created link component
    """
    # Create sketch
    sketch = doc.addObject('Sketcher::SketchObject', f'{name}_Sketch')
    
    # Define link geometry
    sketch.addGeometry(Part.LineSegment(
        App.Vector(0, -width/2, 0),
        App.Vector(length, -width/2, 0)
    ), False)
    sketch.addGeometry(Part.LineSegment(
        App.Vector(length, -width/2, 0),
        App.Vector(length, width/2, 0)
    ), False)
    sketch.addGeometry(Part.LineSegment(
        App.Vector(length, width/2, 0),
        App.Vector(0, width/2, 0)
    ), False)
    sketch.addGeometry(Part.LineSegment(
        App.Vector(0, width/2, 0),
        App.Vector(0, -width/2, 0)
    ), False)
    
    # Add bearing holes
    pin_diameter = 6
    sketch.addGeometry(Part.Circle(
        App.Vector(0, 0, 0), 
        App.Vector(0, 0, 1), 
        pin_diameter/2
    ), False)
    sketch.addGeometry(Part.Circle(
        App.Vector(length, 0, 0), 
        App.Vector(0, 0, 1), 
        pin_diameter/2
    ), False)
    
    # Create 3D part
    pad = doc.addObject("Part::Extrusion", f"{name}_Pad")
    pad.Base = sketch
    pad.DirMode = "Normal"
    pad.LengthFwd = thickness
    
    # Add material properties
    pad.addProperty("App::PropertyFloat", "Density", "Material", "Material density")
    pad.Density = material_density
    
    return pad

def create_assembly():
    """Create complete mechanism assembly with constraints"""
    links = {}
    
    # Create all links
    ${Object.entries(params).map(([key, param], index) => {
        if (param.name.toLowerCase().includes('link') || param.name.toLowerCase().includes('length')) {
            return `    links['${key}'] = create_link('${key.charAt(0).toUpperCase() + key.slice(1)}', ${key})`;
        }
        return '';
    }).filter(Boolean).join('\n')}
    
    # Position components (initial configuration)
    # Note: For full assembly constraints, use Assembly4 workbench
    
    return links

# Generate mechanism
print("Creating ${mechanism.name}...")
components = create_assembly()

# Analysis functions
def calculate_workspace():
    """Calculate mechanism workspace"""
    # Add workspace calculation logic here
    pass

def perform_kinematic_analysis():
    """Perform kinematic analysis"""
    # Add kinematic analysis logic here
    pass

def generate_manufacturing_drawings():
    """Generate technical drawings"""
    # Add drawing generation logic here
    pass

# Run analysis
calculate_workspace()
perform_kinematic_analysis()

# Finalize document
doc.recompute()
print(f"${mechanism.name} model created successfully!")
print(f"Parameters: ${JSON.stringify(params)}")

# Save document
doc.saveAs("${mechanismType}_complete_model.FCStd")

print("\\nNext Steps:")
print("1. Review component geometry and tolerances")
print("2. Add assembly constraints using Assembly4 workbench")
print("3. Perform finite element analysis if needed")
print("4. Generate manufacturing drawings")
print("5. Export STL files for 3D printing or manufacturing")
`;
}
```

## 🎨 UI Customization

### **Adding New Control Types**

```javascript
// Add to updateMechanismControls function
function createAdvancedControls(parameters) {
    return Object.entries(parameters).map(([key, param]) => {
        if (param.type === 'dropdown') {
            return `
                <div class="control-row">
                    <label>${param.name}:</label>
                    <select id="${key}-control" onchange="updateParameter('${key}', this.value)">
                        ${param.options.map(opt => 
                            `<option value="${opt.value}" ${opt.value === param.value ? 'selected' : ''}>${opt.label}</option>`
                        ).join('')}
                    </select>
                </div>
            `;
        } else if (param.type === 'checkbox') {
            return `
                <div class="control-row">
                    <label>
                        <input type="checkbox" id="${key}-control" ${param.value ? 'checked' : ''} 
                               onchange="updateParameter('${key}', this.checked)">
                        ${param.name}
                    </label>
                </div>
            `;
        } else {
            // Default range slider
            return `
                <div class="control-row">
                    <label>${param.name}:</label>
                    <input type="range" id="${key}-control" min="${param.min}" max="${param.max}" 
                           value="${param.value}" step="${param.step || 1}"
                           oninput="updateParameter('${key}', this.value)">
                    <span id="${key}-value">${param.value}</span>
                </div>
            `;
        }
    }).join('');
}
```

### **Custom Visualization Features**

```javascript
function drawAdvancedVisualization() {
    // Add grid overlay
    drawGrid();
    
    // Add coordinate system
    drawCoordinateSystem();
    
    // Add dimension lines
    drawDimensions();
    
    // Add velocity vectors
    if (showVelocityVectors) {
        drawVelocityVectors();
    }
    
    // Add force vectors
    if (showForceVectors) {
        drawForceVectors();
    }
}

function drawGrid() {
    ctx.strokeStyle = 'rgba(0, 0, 0, 0.1)';
    ctx.lineWidth = 1;
    
    const gridSize = 20;
    const canvasWidth = ctx.canvas.width;
    const canvasHeight = ctx.canvas.height;
    
    // Vertical lines
    for (let x = 0; x <= canvasWidth; x += gridSize) {
        ctx.beginPath();
        ctx.moveTo(x, 0);
        ctx.lineTo(x, canvasHeight);
        ctx.stroke();
    }
    
    // Horizontal lines
    for (let y = 0; y <= canvasHeight; y += gridSize) {
        ctx.beginPath();
        ctx.moveTo(0, y);
        ctx.lineTo(canvasWidth, y);
        ctx.stroke();
    }
}
```

## 🔧 Advanced Features

### **Animation System Enhancement**

```javascript
class AnimationController {
    constructor() {
        this.isPlaying = false;
        this.speed = 30; // RPM
        this.direction = 1; // 1 for forward, -1 for reverse
        this.frameRate = 60; // FPS
        this.time = 0;
    }
    
    start() {
        if (this.isPlaying) return;
        this.isPlaying = true;
        this.animate();
    }
    
    stop() {
        this.isPlaying = false;
    }
    
    animate() {
        if (!this.isPlaying) return;
        
        // Calculate time step
        const dt = (this.speed * this.direction * 2 * Math.PI) / (60 * this.frameRate);
        this.time += dt;
        
        // Update global angle
        angle = this.time;
        if (angle > 2 * Math.PI) {
            angle -= 2 * Math.PI;
            this.time -= 2 * Math.PI;
        }
        if (angle < 0) {
            angle += 2 * Math.PI;
            this.time += 2 * Math.PI;
        }
        
        // Redraw mechanism
        drawMechanism();
        
        // Schedule next frame
        requestAnimationFrame(() => this.animate());
    }
    
    setSpeed(rpm) {
        this.speed = Math.max(1, Math.min(120, rpm));
    }
    
    reverse() {
        this.direction *= -1;
    }
}

// Usage
const animationController = new AnimationController();
```

### **Performance Optimization**

```javascript
// Implement canvas caching for static elements
class CanvasCache {
    constructor() {
        this.backgroundCanvas = document.createElement('canvas');
        this.backgroundCtx = this.backgroundCanvas.getContext('2d');
        this.isDirty = true;
    }
    
    updateBackground(width, height) {
        if (!this.isDirty) return;
        
        this.backgroundCanvas.width = width;
        this.backgroundCanvas.height = height;
        
        // Draw static elements (grid, coordinate system, etc.)
        this.drawStaticElements();
        
        this.isDirty = false;
    }
    
    drawStaticElements() {
        // Draw grid, axes, labels, etc.
        this.drawGrid();
        this.drawCoordinateSystem();
    }
    
    render(ctx) {
        ctx.drawImage(this.backgroundCanvas, 0, 0);
    }
    
    invalidate() {
        this.isDirty = true;
    }
}
```

## 🧪 Testing and Validation

### **Unit Testing Framework**

```javascript
// Simple testing framework for mechanism calculations
class MechanismTester {
    constructor() {
        this.tests = [];
        this.results = [];
    }
    
    addTest(name, testFunction) {
        this.tests.push({ name, testFunction });
    }
    
    runTests() {
        this.results = [];
        
        this.tests.forEach(test => {
            try {
                const result = test.testFunction();
                this.results.push({
                    name: test.name,
                    passed: result,
                    error: null
                });
                console.log(`✓ ${test.name}: PASSED`);
            } catch (error) {
                this.results.push({
                    name: test.name,
                    passed: false,
                    error: error.message
                });
                console.error(`✗ ${test.name}: FAILED - ${error.message}`);
            }
        });
        
        return this.results;
    }
    
    generateReport() {
        const passed = this.results.filter(r => r.passed).length;
        const total = this.results.length;
        
        console.log(`\n=== Test Report ===`);
        console.log(`Total Tests: ${total}`);
        console.log(`Passed: ${passed}`);
        console.log(`Failed: ${total - passed}`);
        console.log(`Success Rate: ${(passed/total*100).toFixed(1)}%`);
        
        return this.results;
    }
}

// Example test cases
const tester = new MechanismTester();

tester.addTest('Four-bar Grashof Condition', () => {
    const L1 = 100, L2 = 40, L3 = 120, L4 = 80;
    const s = Math.min(L1, L2, L3, L4);
    const l = Math.max(L1, L2, L3, L4);
    const p_q = L1 + L2 + L3 + L4 - s - l;
    
    // Should satisfy Grashof condition
    return s + l <= p_q;
});

tester.addTest('Slider-crank Position Calculation', () => {
    const r = 50, l = 150, offset = 0;
    const theta = Math.PI / 4; // 45 degrees
    
    const expected_x = r * Math.cos(theta) + Math.sqrt(l*l - (r * Math.sin(theta) - offset)**2);
    const calculated_x = 35.355 + 144.886; // Expected result
    
    return Math.abs(expected_x - calculated_x) < 0.1;
});

// Run tests during development
// tester.runTests();
// tester.generateReport();
```

### **Validation Guidelines**

```javascript
// Mechanism validation functions
function validateMechanismGeometry(mechanismType) {
    const params = mechanisms[mechanismType].parameters;
    const errors = [];
    
    switch(mechanismType) {
        case 'fourbar':
            const L1 = params.link1.value;
            const L2 = params.link2.value;
            const L3 = params.link3.value;
            const L4 = params.link4.value;
            
            // Check triangle inequality for all combinations
            if (L2 + L3 <= L1 + L4) errors.push("Links cannot form closed loop");
            if (L1 + L2 <= L3 + L4) errors.push("Links cannot form closed loop");
            if (L1 + L3 <= L2 + L4) errors.push("Links cannot form closed loop");
            if (L1 + L4 <= L2 + L3) errors.push("Links cannot form closed loop");
            
            break;
            
        case 'slidercrank':
            const r = params.crank.value;
            const l = params.rod.value;
            const offset = Math.abs(params.offset.value);
            
            if (l <= r + offset) errors.push("Connecting rod too short for given offset");
            
            break;
    }
    
    return errors;
}

function validateExperimentData() {
    if (experimentData.length === 0) {
        return ["No experimental data available"];
    }
    
    const errors = [];
    
    // Check for NaN values
    experimentData.forEach((row, index) => {
        Object.entries(row).forEach(([key, value]) => {
            if (typeof value === 'number' && isNaN(value)) {
                errors.push(`NaN value found in row ${index}, column ${key}`);
            }
        });
    });
    
    // Check for reasonable value ranges
    const numericColumns = Object.keys(experimentData[0]).filter(key => 
        typeof experimentData[0][key] === 'number'
    );
    
    numericColumns.forEach(column => {
        const values = experimentData.map(row => parseFloat(row[column]));
        const max = Math.max(...values);
        const min = Math.min(...values);
        
        if (max - min === 0) {
            errors.push(`Column ${column} has constant values (no variation)`);
        }
        
        if (Math.abs(max) > 1e6 || Math.abs(min) > 1e6) {
            errors.push(`Column ${column} has unreasonably large values`);
        }
    });
    
    return errors;
}
```

## 📚 Educational Integration

### **Learning Module System**

```javascript
// Educational content management
const learningModules = {
    kinematics_basics: {
        title: "Kinematics Fundamentals",
        concepts: [
            {
                name: "Position Analysis",
                description: "Understanding position relationships in mechanisms",
                interactive_demo: "fourbar_position",
                equations: [
                    "Position vectors: r⃗ᵢ = xᵢî + yᵢĵ",
                    "Closure equation: Σr⃗ᵢ = 0"
                ],
                exercises: [
                    "Calculate position of point C for θ₂ = 45°",
                    "Find all possible positions for given link lengths"
                ]
            },
            {
                name: "Velocity Analysis", 
                description: "Velocity relationships and instant centers",
                interactive_demo: "fourbar_velocity",
                equations: [
                    "Velocity: v⃗ = dr⃗/dt",
                    "Relative velocity: v⃗ᶜ = v⃗ᴮ + ω⃗ × r⃗ᴮᶜ"
                ]
            }
        ]
    },
    
    mechanism_design: {
        title: "Mechanism Design Principles",
        concepts: [
            {
                name: "Grashof's Law",
                description: "Determining mechanism mobility and rotation capability",
                interactive_demo: "grashof_analyzer",
                equations: [
                    "s + l ≤ p + q (Grashof condition)",
                    "s = shortest link, l = longest link"
                ]
            }
        ]
    }
};

function loadLearningModule(moduleId, conceptId) {
    const module = learningModules[moduleId];
    const concept = module.concepts.find(c => c.name.toLowerCase().includes(conceptId));
    
    // Display concept information
    displayConceptInfo(concept);
    
    // Load interactive demonstration
    if (concept.interactive_demo) {
        loadInteractiveDemo(concept.interactive_demo);
    }
}

function displayConceptInfo(concept) {
    const infoPanel = document.getElementById('mechanism-info');
    infoPanel.innerHTML = `
        <h4>${concept.name}</h4>
        <p>${concept.description}</p>
        
        <h5>Key Equations:</h5>
        <ul>
            ${concept.equations.map(eq => `<li>${eq}</li>`).join('')}
        </ul>
        
        ${concept.exercises ? `
        <h5>Practice Exercises:</h5>
        <ul>
            ${concept.exercises.map(ex => `<li>${ex}</li>`).join('')}
        </ul>
        ` : ''}
    `;
}
```

### **Assessment System**

```javascript
class MechanismAssessment {
    constructor() {
        this.questions = [];
        this.userAnswers = [];
        this.currentQuestion = 0;
    }
    
    loadQuestionSet(mechanismType) {
        switch(mechanismType) {
            case 'fourbar':
                this.questions = [
                    {
                        type: 'multiple_choice',
                        question: 'What determines if a four-bar linkage can make a complete rotation?',
                        options: [
                            'The length of the ground link',
                            'Grashof\'s condition (s + l ≤ p + q)',
                            'The transmission angle',
                            'The coupler curve shape'
                        ],
                        correct: 1,
                        explanation: 'Grashof\'s condition determines mobility. When satisfied, at least one link can make a complete rotation.'
                    },
                    {
                        type: 'calculation',
                        question: 'Given L1=100mm, L2=40mm, L3=120mm, L4=80mm, calculate the Grashof parameter (s+l)-(p+q)',
                        setup_mechanism: {
                            parameters: {link1: 100, link2: 40, link3: 120, link4: 80}
                        },
                        answer_type: 'numeric',
                        correct_answer: -40,
                        tolerance: 1,
                        explanation: 's=40, l=120, p=80, q=100. Therefore (40+120)-(80+100) = -40'
                    }
                ];
                break;
        }
    }
    
    presentQuestion() {
        const question = this.questions[this.currentQuestion];
        
        if (question.setup_mechanism) {
            // Configure mechanism for the question
            this.setupMechanismForQuestion(question.setup_mechanism);
        }
        
        // Display question interface
        this.displayQuestion(question);
    }
    
    checkAnswer(userAnswer) {
        const question = this.questions[this.currentQuestion];
        let isCorrect = false;
        
        switch(question.type) {
            case 'multiple_choice':
                isCorrect = userAnswer === question.correct;
                break;
            case 'calculation':
                const numericAnswer = parseFloat(userAnswer);
                isCorrect = Math.abs(numericAnswer - question.correct_answer) <= question.tolerance;
                break;
        }
        
        this.userAnswers.push({
            question: this.currentQuestion,
            answer: userAnswer,
            correct: isCorrect,
            explanation: question.explanation
        });
        
        return isCorrect;
    }
    
    generateReport() {
        const correct = this.userAnswers.filter(a => a.correct).length;
        const total = this.userAnswers.length;
        const percentage = (correct / total * 100).toFixed(1);
        
        return {
            score: percentage,
            correct: correct,
            total: total,
            details: this.userAnswers
        };
    }
}
```

## 🔧 Advanced Configuration

### **Theme System**

```javascript
const themes = {
    default: {
        primary: '#667eea',
        secondary: '#764ba2',
        accent: '#4ECDC4',
        background: '#f5f5f5',
        surface: 'white',
        text: '#333'
    },
    dark: {
        primary: '#7c3aed',
        secondary: '#a855f7',
        accent: '#06d6a0',
        background: '#1a1a1a',
        surface: '#2d2d2d',
        text: '#ffffff'
    },
    engineering: {
        primary: '#2563eb',
        secondary: '#1d4ed8',
        accent: '#f59e0b',
        background: '#f8fafc',
        surface: 'white',
        text: '#1e293b'
    }
};

function applyTheme(themeName) {
    const theme = themes[themeName];
    const root = document.documentElement;
    
    Object.entries(theme).forEach(([property, value]) => {
        root.style.setProperty(`--color-${property}`, value);
    });
    
    // Update CSS custom properties
    document.querySelector(':root').style.cssText = `
        --color-primary: ${theme.primary};
        --color-secondary: ${theme.secondary};
        --color-accent: ${theme.accent};
        --color-background: ${theme.background};
        --color-surface: ${theme.surface};
        --color-text: ${theme.text};
    `;
}
```

### **Plugin System Architecture**

```javascript
class PluginManager {
    constructor() {
        this.plugins = new Map();
        this.hooks = new Map();
    }
    
    registerPlugin(name, plugin) {
        if (this.validatePlugin(plugin)) {
            this.plugins.set(name, plugin);
            plugin.initialize();
            console.log(`Plugin "${name}" registered successfully`);
        }
    }
    
    validatePlugin(plugin) {
        const required = ['name', 'version', 'initialize'];
        return required.every(prop => prop in plugin);
    }
    
    registerHook(hookName, callback) {
        if (!this.hooks.has(hookName)) {
            this.hooks.set(hookName, []);
        }
        this.hooks.get(hookName).push(callback);
    }
    
    executeHook(hookName, data) {
        if (this.hooks.has(hookName)) {
            this.hooks.get(hookName).forEach(callback => {
                try {
                    callback(data);
                } catch (error) {
                    console.error(`Hook "${hookName}" error:`, error);
                }
            });
        }
    }
}

// Example plugin
const ExamplePlugin = {
    name: "Advanced Analytics",
    version: "1.0.0",
    
    initialize() {
        // Add new experiment types
        this.addExperimentType('statistical-analysis', this.runStatisticalAnalysis);
        
        // Register for hooks
        pluginManager.registerHook('experiment-complete', this.onExperimentComplete);
    },
    
    addExperimentType(id, handler) {
        // Extend the experiment system
        if (!window.customExperiments) {
            window.customExperiments = new Map();
        }
        window.customExperiments.set(id, handler);
    },
    
    runStatisticalAnalysis() {
        // Custom experiment implementation
        const stats = this.calculateStatistics(experimentData);
        this.displayStatistics(stats);
    },
    
    onExperimentComplete(data) {
        // Automatic analysis after experiments
        console.log('Running automatic statistical analysis...');
    }
};

// Usage
const pluginManager = new PluginManager();
pluginManager.registerPlugin('advanced-analytics', ExamplePlugin);
```

## 🚀 Deployment and Distribution

### **Build Process (Optional)**

While the system is designed to run as a single HTML file, you can optionally create a build process for advanced features:

```javascript
// build.js - Node.js build script (optional)
const fs = require('fs');
const path = require('path');

class Builder {
    constructor() {
        this.template = fs.readFileSync('src/template.html', 'utf8');
        this.mechanisms = this.loadMechanisms();
    }
    
    loadMechanisms() {
        const mechanismsDir = 'src/mechanisms';
        const mechanisms = {};
        
        fs.readdirSync(mechanismsDir).forEach(file => {
            if (file.endsWith('.js')) {
                const mechanismName = path.basename(file, '.js');
                const mechanismCode = fs.readFileSync(path.join(mechanismsDir, file), 'utf8');
                mechanisms[mechanismName] = mechanismCode;
            }
        });
        
        return mechanisms;
    }
    
    build() {
        let html = this.template;
        
        // Inject mechanism definitions
        const mechanismsCode = Object.entries(this.mechanisms)
            .map(([name, code]) => code)
            .join('\n\n');
        
        html = html.replace('{{MECHANISMS}}', mechanismsCode);
        
        // Minify if needed
        if (process.env.NODE_ENV === 'production') {
            html = this.minify(html);
        }
        
        fs.writeFileSync('dist/index.html', html);
        console.log('Build complete: dist/index.html');
    }
    
    minify(html) {
        // Simple minification - remove unnecessary whitespace
        return html
            .replace(/\s+/g, ' ')
            .replace(/>\s+</g, '><')
            .trim();
    }
}

// Run build
new Builder().build();
```

### **Version Management**

```javascript
const VERSION_INFO = {
    version: "1.0.0",
    buildDate: new Date().toISOString(),
    mechanisms: Object.keys(mechanisms).length,
    experiments: Object.values(mechanisms).reduce((total, m) => total + m.experiments.length, 0),
    
    getInfo() {
        return `
SiliconWit 2D Mechanisms Analyzer v${this.version}
Built: ${this.buildDate}
Mechanisms: ${this.mechanisms}
Experiments: ${this.experiments}
        `.trim();
    },
    
    checkForUpdates() {
        // Implement update checking logic
        console.log('Checking for updates...');
    }
};

// Display version info in console
console.log(VERSION_INFO.getInfo());
```

## 📖 Documentation Standards

### **Code Documentation**

```javascript
/**
 * Draws a four-bar linkage mechanism with real-time kinematic visualization
 * 
 * This function implements the position analysis for a four-bar linkage using
 * geometric constraint solving. The mechanism is drawn with professional
 * styling including proper joint representations and optional trajectory tracing.
 * 
 * @function drawFourBarLinkage
 * @description Renders a four-bar linkage mechanism on the canvas
 * 
 * @requires Global variable 'angle' - current input angle in radians
 * @requires Global object 'mechanisms.fourbar.parameters' - link length parameters
 * 
 * @example
 * // Set mechanism parameters
 * mechanisms.fourbar.parameters.link1.value = 100; // Ground link
 * mechanisms.fourbar.parameters.link2.value = 40;  // Input link
 * mechanisms.fourbar.parameters.link3.value = 120; // Coupler link
 * mechanisms.fourbar.parameters.link4.value = 80;  // Output link
 * 
 * // Set input angle and draw
 * angle = Math.PI / 4; // 45 degrees
 * drawFourBarLinkage();
 * 
 * @algorithm
 * 1. Extract link lengths from parameter object
 * 2. Calculate position of point C using input angle
 * 3. Solve for point D using circle intersection method
 * 4. Validate geometric constraints (triangle inequality)
 * 5. Draw mechanism components using helper functions
 * 6. Add labels and optional trajectory visualization
 * 
 * @complexity O(1) - Constant time geometric calculations
 * 
 * @see {@link drawLink} For link rendering
 * @see {@link drawJoint} For joint rendering  
 * @see {@link drawCouplerCurve} For trajectory tracing
 * 
 * @throws Will display "Invalid linkage configuration" if links cannot form closed loop
 * 
 * @version 1.0.0
 * @since 1.0.0
 * @author SiliconWit Development Team
 */
function drawFourBarLinkage() {
    // Implementation...
}

/**
 * Mechanism configuration object defining all available mechanisms
 * 
 * @typedef {Object} MechanismConfig
 * @property {string} name - Display name for the mechanism
 * @property {string} description - Brief description for UI display
 * @property {Array<ExperimentConfig>} experiments - Available experiments
 * @property {Object<string, ParameterConfig>} parameters - Adjustable parameters
 * @property {Array<string>} info - Educational information and links
 * 
 * @typedef {Object} ExperimentConfig
 * @property {string} id - Unique experiment identifier
 * @property {string} name - Display name for experiment
 * @property {string} desc - Description of experiment purpose
 * 
 * @typedef {Object} ParameterConfig
 * @property {string} name - Parameter display name with units
 * @property {number} value - Default/current value
 * @property {number} min - Minimum allowed value
 * @property {number} max - Maximum allowed value
 * @property {number} [step] - Optional step size for controls
 */
```

### **API Documentation**

```javascript
/**
 * @namespace MechanismAPI
 * @description Public API for extending the mechanism analyzer
 */

/**
 * Add a new mechanism to the system
 * 
 * @memberof MechanismAPI
 * @function addMechanism
 * @param {string} id - Unique mechanism identifier
 * @param {MechanismConfig} config - Mechanism configuration object
 * @param {Function} drawFunction - Function to render the mechanism
 * @param {Object<string, Function>} experiments - Experiment implementations
 * 
 * @example
 * MechanismAPI.addMechanism('pantograph', {
 *   name: 'Pantograph Mechanism',
 *   description: 'Parallel motion generation mechanism',
 *   parameters: {
 *     link_length: { name: 'Link Length (mm)', value: 100, min: 50, max: 200 }
 *   },
 *   experiments: [
 *     { id: 'motion-study', name: 'Motion Study', desc: 'Analyze parallel motion' }
 *   ],
 *   info: ['Creates parallel motion', 'Used in drafting instruments']
 * }, drawPantograph, {
 *   'motion-study': runPantographMotionStudy
 * });
 */
```

## 🤝 Contributing Guidelines

### **Development Workflow**

1. **Fork the Repository**
   ```bash
   git clone https://github.com/SiliconWit/2d-mechanisms-analyzer.git
   cd 2d-mechanisms-analyzer
   ```

2. **Create Feature Branch**
   ```bash
   git checkout -b feature/new-mechanism-name
   ```

3. **Development Process**
   - Add mechanism configuration to `mechanisms` object
   - Implement drawing function following existing patterns
   - Create experiment functions with proper data collection
   - Add comprehensive documentation
   - Test thoroughly in multiple browsers

4. **Testing Checklist**
   - [ ] Mechanism renders correctly at all parameter values
   - [ ] Animation runs smoothly without performance issues
   - [ ] Experiments generate valid data
   - [ ] Export functions work properly
   - [ ] Responsive design works on mobile devices
   - [ ] No console errors or warnings

5. **Commit Standards**
   ```bash
   git commit -m "feat: add pantograph mechanism with motion analysis
   
   - Implement drawing function with parallel motion visualization
   - Add motion study experiment with trajectory analysis
   - Include educational content and CAD export
   - Add comprehensive documentation and examples"
   ```

6. **Pull Request Process**
   - Ensure all tests pass
   - Update documentation
   - Add example usage
   - Request review from maintainers

### **Code Style Guidelines**

```javascript
// Function naming: descriptive verbs
function calculateVelocityVector() { /* ... */ }
function drawMechanismComponent() { /* ... */ }
function validateGeometricConstraints() { /* ... */ }

// Variable naming: descriptive nouns
const linkLength = 100;
const jointPosition = [x, y];
const experimentData = [];

// Constants: UPPER_SNAKE_CASE
const DEFAULT_ANIMATION_SPEED = 30;
const MAX_PARAMETER_VALUE = 1000;

// Object properties: camelCase
const mechanismConfig = {
    displayName: "Four-Bar Linkage",
    parameterValues: {},
    experimentTypes: []
};

// Comments: Clear and educational
// Calculate the position of point D using circle intersection method
// This implements the geometric constraint that point D must be:
// 1. Distance L3 from point C (coupler link constraint)
// 2. Distance L4 from point B (output link constraint)
```

## 🐛 Troubleshooting

### **Common Issues**

**Issue: Mechanism not drawing**
```javascript
// Debug checklist:
1. Check console for JavaScript errors
2. Verify mechanism is added to switch statement
3. Ensure parameters are properly defined
4. Check canvas context is available

// Debug code:
console.log('Current mechanism:', currentMechanism);
console.log('Mechanism config:', mechanisms[currentMechanism]);
console.log('Canvas context:', ctx);
```

**Issue: Animation performance problems**
```javascript
// Performance optimization:
1. Reduce drawing complexity in animation loop
2. Use canvas caching for static elements  
3. Implement frame rate limiting
4. Optimize mathematical calculations

// Performance monitoring:
const startTime = performance.now();
drawMechanism();
const endTime = performance.now();
console.log(`Draw time: ${endTime - startTime}ms`);
```

**Issue: Experiment data not generating**
```javascript
// Debug experiment system:
console.log('Current experiment:', currentExperiment);
console.log('Experiment data length:', experimentData.length);
console.log('Sample data:', experimentData[0]);

// Validation:
function debugExperiment() {
    if (!currentExperiment) {
        console.error('No experiment selected');
        return false;
    }
    
    if (experimentData.length === 0) {
        console.error('No data generated');
        return false;
    }
    
    return true;
}
```

### **Browser Compatibility**

**Supported Browsers:**
- Chrome 60+
- Firefox 55+  
- Safari 11+
- Edge 79+

**Required Features:**
- HTML5 Canvas
- CSS Grid Layout
- ES6 Classes and Arrow Functions
- RequestAnimationFrame API

**Polyfills (if needed):**
```javascript
// RequestAnimationFrame polyfill
if (!window.requestAnimationFrame) {
    window.requestAnimationFrame = function(callback) {
        return setTimeout(callback, 1000 / 60);
    };
}
```

## 📊 Performance Considerations

### **Optimization Strategies**

1. **Canvas Optimization**
   - Use `requestAnimationFrame` for smooth animation
   - Implement dirty rectangle rendering for partial updates
   - Cache static background elements
   - Minimize canvas state changes

2. **Memory Management**
   - Clear experiment data when switching mechanisms
   - Avoid memory leaks in animation loops
   - Use object pooling for frequently created objects

3. **Computational Efficiency**
   - Pre-calculate constants outside animation loops
   - Use lookup tables for trigonometric functions
   - Implement early termination for invalid configurations

### **Scalability Guidelines**

- **Maximum Mechanisms**: 20-30 (UI constraint)
- **Maximum Experiments per Mechanism**: 10-15
- **Maximum Data Points per Experiment**: 1000-5000
- **Animation Frame Rate**: 30-60 FPS
- **File Size Target**: <500KB for complete application

## 🔒 Security Considerations

### **Safe Practices**

1. **Input Validation**
   ```javascript
   function validateParameterInput(value, min, max) {
       const num = parseFloat(value);
       if (isNaN(num)) return false;
       return num >= min && num <= max;
   }
   ```

2. **XSS Prevention**
   ```javascript
   function sanitizeUserInput(input) {
       return input
           .replace(/</g, '&lt;')
           .replace(/>/g, '&gt;')
           .replace(/"/g, '&quot;');
   }
   ```

3. **Content Security Policy**
   ```html
   <meta http-equiv="Content-Security-Policy" 
         content="default-src 'self'; script-src 'self' 'unsafe-inline';">
   ```

## 📈 Future Roadmap

### **Planned Features**

1. **3D Mechanism Support**
   - WebGL-based 3D rendering
   - Spatial mechanism analysis
   - 3D printing integration

2. **Advanced Analysis**
   - Finite element analysis integration
   - Dynamic force analysis
   - Optimization algorithms

3. **Collaboration Features**
   - Mechanism sharing via URL parameters
   - Real-time collaboration tools
   - Community mechanism library

4. **Educational Enhancements**
   - Interactive tutorials
   - Adaptive learning system
   - Progress tracking

### **Technical Improvements**

1. **Performance**
   - WebAssembly for heavy calculations
   - Web Workers for parallel processing
   - Progressive loading of mechanisms

2. **Accessibility**
   - Screen reader support
   - Keyboard navigation
   - High contrast modes

3. **Integration**
   - LMS (Learning Management System) integration
   - CAD software plugins
   - Mobile app versions

## 📞 Support and Community

### **Getting Help**

1. **Documentation**: Comprehensive README and inline comments
2. **Examples**: Complete mechanism implementations provided
3. **Issues**: GitHub issue tracker for bug reports and feature requests
4. **Discussions**: GitHub Discussions for questions and community support

### **Contributing**

1. **Code Contributions**: New mechanisms, experiments, and features
2. **Documentation**: Tutorials, examples, and educational content
3. **Testing**: Bug reports, browser compatibility testing
4. **Translation**: Multi-language support

### **Educational Partnerships**

We welcome partnerships with:
- Engineering schools and universities
- Online learning platforms
- Textbook publishers
- Educational technology companies

---

## 📄 License

```
Copyright 2024 SiliconWit

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for complete details.

### **Why Apache 2.0?**

The Apache 2.0 license provides:
- **Permissive Use**: Freedom to use, modify, and distribute
- **Patent Protection**: Express grant of patent rights from contributors
- **Commercial Friendly**: Can be used in commercial and proprietary projects
- **Attribution Required**: Must preserve copyright and license notices
- **Educational Focus**: Ideal for academic and educational projects

### **License Compatibility**

- ✅ **Educational Use**: Universities, schools, online courses
- ✅ **Commercial Use**: Companies, startups, commercial software
- ✅ **Open Source Projects**: Compatible with most open source licenses
- ✅ **Modification**: Create derivative works and modifications
- ✅ **Distribution**: Share and redistribute the software

### **Attribution Requirements**

When using this software, you must:
1. **Include License**: Provide a copy of the Apache 2.0 license
2. **Preserve Notices**: Keep all copyright, patent, trademark notices
3. **State Changes**: Document any modifications made to the original
4. **Include Attribution**: Credit SiliconWit and original contributors

## 🙏 Acknowledgments

- Educational institutions providing feedback and requirements
- Open source community for tools and libraries
- Students and educators testing the system
- Contributors improving the codebase

---

**For more information, visit: [https://siliconwit.com/education/planar-mechanics/](https://siliconwit.com/education/planar-mechanics/)**

**Repository: [https://github.com/SiliconWit/2d-mechanisms-analyzer](https://github.com/SiliconWit/2d-mechanisms-analyzer)**