# 🎯 PRP-BASED FINANCIAL MODEL LAYER BUILDING
## Product Requirements Prompt with Technical Lessons Learned Integration

---

## 📋 PROJECT OVERVIEW

**Project Name:** [LAYER NAME] Financial Model Development  
**Objective:** Build complete [Green Layer (Revenue) / Orange Layer (Operating Costs)] with 10-year projections and SA compliance  
**Technology Stack:** Python (openpyxl) + MCP Excel Tools + SA Research Benchmarks + Lessons Learned Patterns  
**Deliverables:** Investment-grade Excel layer with professional presentation, robust reference system, and IDC submission readiness

---

## 🔧 CRITICAL TOOL USAGE RULES & TECHNICAL CONTEXT

**TOOL SEPARATION - NON-NEGOTIABLE:**
- 🔍 **MCP TOOLS (READ-ONLY)**: Analysis, validation, checking, reporting - NEVER modify Excel files
- 🔧 **PYTHON TOOLS (WRITE OPERATIONS)**: Building, creating, modifying Excel sheets and formulas

**MCP Usage Examples:**
```bash
# Analyse current state
excel-negokaz:excel_describe_sheets(fileAbsolutePath='[WORKBOOK_PATH]')
excel-negokaz:excel_read_sheet(sheetName='Rev_Accommodation', showFormula=true)

# Validate after building
excel-negokaz:excel_read_sheet(sheetName='Cost_Accommodation', range='A1:N50')
```

**Python Usage Examples with Lessons Learnt:**
```python
# Build and modify sheets using robust patterns
import openpyxl
from openpyxl.styles import PatternFill, Font, Alignment

# LESSON: Always use exact RGB colour values
YELLOW_FILL = PatternFill(start_color="FFFF00", end_color="FFFF00", fill_type="solid")
CENTURY_GOTHIC = Font(name='Century Gothic', size=11)

wb = openpyxl.load_workbook('[WORKBOOK_PATH]')
ws = wb.create_sheet('Rev_Accommodation')

# LESSON: Safe cell writing with merged cell handling
def safe_cell_write(ws, cell_ref, value, fill=None, font=None):
    """Write to cell with full error handling from lessons learnt"""
    try:
        cell = ws[cell_ref]
        if cell.coordinate in ws.merged_cells:
            return False  # Skip merged cells
        cell.value = value
        if fill: cell.fill = fill
        if font: cell.font = font
        return True
    except Exception as e:
        print(f"Failed to write {cell_ref}: {e}")
        return False

wb.save('[WORKBOOK_PATH]')
```

---

## 📚 CONTEXT & BACKGROUND REQUIREMENTS

### Business Context
- **Investment Scale**: R50-60M youth development & adventure training destination
- **Capacity**: 190-bed facility across capsule pods, bunks, and family rooms  
- **Location**: 21 hectares in UNESCO Biosphere Reserve (Hartbeespoort, South Africa)
- **Funding Structure**: IDC 70-30 model with grant compliance requirements
- **Success Criteria**: Investment-grade presentation suitable for development finance institution submission

### International Expansion Foundation
- **Core Framework**: South African foundation model with jurisdiction adaptability
- **Target Markets**: USA, UK, EU financial modelling standards
- **Regulatory Modularity**: Country-specific compliance modules
- **Currency Flexibility**: Multi-currency support architecture
- **Legal Framework**: Adaptable to different corporate structures

### Technical Context - MANDATORY CONTEXT LOADING
**READ ALL CONTEXT ENGINEERING FILES FIRST:**
- Read `CLAUDE.md` - Tool usage rules and autonomous decision-making
- Read `HOSTEL_DIARY_PROJECT_SPECIFICATION.md` - Business requirements
- Read `BUILD_SEQUENCE_AND_REFERENCING_GUIDE.md` - Technical architecture
- Read `EXCEL_DESIGN_STANDARDS.md` - Design standards enforcement
- Read `CONTEXT_ENGINEERING_README.md` - Context engineering framework
- Read `REFERENCE_MANAGEMENT_PROTOCOLS.md` - Reference architecture
- Read `LESSONS_LEARNED_TECHNICAL.md` - Critical technical lessons

**LOAD LAYER-SPECIFIC STRATEGY:**
- Read `10_YEAR_REVENUE_PROJECTION_STRATEGY.md` (for Green Layer)
- Read `ORANGE_LAYER_CONTEXT_ENGINEERING.md` (for Orange Layer)

**LOAD PRP IMPLEMENTATION FRAMEWORKS:**
- Execute `PRPs/templates/green_layer_autonomous_prp.md` (for Green Layer)
- Execute `PRPs/templates/orange_layer_autonomous_prp.md` (for Orange Layer)

**LOAD RESEARCH & TECHNICAL PATTERNS:**
- Load `research/sa_hospitality_benchmarks.json` for SA market data
- Load `examples/` folder patterns for building templates
- Load existing reference mapping systems
- **CRITICAL**: Apply lessons learnt patterns throughout

---

## 🎨 CRITICAL DESIGN STANDARDS - NON-NEGOTIABLE

### ⚠️ CONTRAST IS EVERYTHING - FUNDAMENTAL DESIGN PRINCIPLE
**CRITICAL: Contrast is one of the most important design elements. Poor contrast renders financial models unusable.**

**CONTRAST REQUIREMENTS:**
- ✅ **Dark text on light backgrounds** - Black text on white/yellow/light blue
- ✅ **Light text on dark backgrounds** - White text on navy/dark green/dark orange
- ✅ **Never light on light** - No yellow text on white backgrounds
- ✅ **Never dark on dark** - No black text on navy backgrounds
- ✅ **Colour blindness consideration** - Contrast ratios must work for colour-blind users
- ✅ **Print compatibility** - Must be readable when printed in black and white

### ⚠️ CENTURY GOTHIC FONT ENFORCEMENT - ABSOLUTE REQUIREMENT
**CRITICAL WARNING: Claude has a persistent, documented tendency to deviate from Century Gothic font. This deviation is STRICTLY FORBIDDEN and will result in immediate failure.**

**NON-NEGOTIABLE FONT REQUIREMENTS:**
```python
# LESSON: Use exact font specification with ZERO tolerance for deviation
CENTURY_GOTHIC_STANDARD = Font(name='Century Gothic', size=11)
CENTURY_GOTHIC_HEADER = Font(name='Century Gothic', size=12, bold=True)
CENTURY_GOTHIC_TITLE = Font(name='Century Gothic', size=14, bold=True)

# MANDATORY: Apply to EVERY cell with content - NO EXCEPTIONS
def enforce_century_gothic_absolute(ws):
    """Apply Century Gothic to all cells - ZERO tolerance for other fonts"""
    font_violations = []
    
    for row in ws.iter_rows():
        for cell in row:
            if cell.value is not None:
                # Force Century Gothic on every cell
                if cell.font.size <= 11:
                    cell.font = CENTURY_GOTHIC_STANDARD
                elif cell.font.size == 12:
                    cell.font = CENTURY_GOTHIC_HEADER
                else:
                    cell.font = CENTURY_GOTHIC_TITLE
                    
                # Validate enforcement
                if cell.font.name != 'Century Gothic':
                    font_violations.append(f"Cell {cell.coordinate}: {cell.font.name}")
    
    if font_violations:
        raise ValueError(f"FONT VIOLATIONS DETECTED: {font_violations}")
    
    return True  # All cells comply
```

**ABSOLUTE FONT REQUIREMENTS:**
- ⚠️ **CENTURY GOTHIC ONLY** - Calibri, Arial, Times New Roman, or ANY other font is FORBIDDEN
- ⚠️ **EVERY SINGLE CELL** with text content must use Century Gothic
- ⚠️ **Headers, data, formulas, labels, notes** - ALL Century Gothic without exception
- ⚠️ **Font sizes**: 11pt for data, 12pt for headers, 14pt for main titles ONLY
- ⚠️ **Bold formatting**: Only for headers and important labels, still Century Gothic
- ⚠️ **Font validation required**: Check every cell after formatting
- ⚠️ **Zero tolerance policy**: Any font deviation constitutes complete failure

### COLOUR STANDARDS (EXACT RGB FROM LESSONS LEARNT)
```python
# LESSON: Use exact RGB values to avoid colour detection issues
COLOUR_STANDARDS = {
    'yellow_input': PatternFill(start_color="FFFF00", end_color="FFFF00", fill_type="solid"),
    'blue_calculation': PatternFill(start_color="BDD7EE", end_color="BDD7EE", fill_type="solid"),
    'green_output': PatternFill(start_color="C6E0B4", end_color="C6E0B4", fill_type="solid"),
    'grey_header': PatternFill(start_color="D9D9D9", end_color="D9D9D9", fill_type="solid"),
    'green_layer': PatternFill(start_color="70AD47", end_color="70AD47", fill_type="solid"),
    'orange_layer': PatternFill(start_color="FF8C00", end_color="FF8C00", fill_type="solid"),
    'navy_summary': PatternFill(start_color="002060", end_color="002060", fill_type="solid")
}

# CRITICAL: Text colour for contrast compliance
TEXT_COLOUR_STANDARDS = {
    'black_on_light': Font(name='Century Gothic', size=11, color="000000"),  # Black on yellow/blue/green
    'white_on_dark': Font(name='Century Gothic', size=11, color="FFFFFF"),   # White on navy/dark colours
    'black_header': Font(name='Century Gothic', size=12, bold=True, color="000000"),
    'white_header': Font(name='Century Gothic', size=12, bold=True, color="FFFFFF")
}
```

### SA English Spelling Standards
**MANDATORY SPELLING REQUIREMENTS:**
- ✅ **Colour** (not color)
- ✅ **Centre** (not center)  
- ✅ **Realise** (not realize)
- ✅ **Analyse** (not analyze)
- ✅ **Capitalise** (not capitalize)
- ✅ **Organisation** (not organization)
- ✅ **Utilise** (not utilize)
- ✅ **Favour** (not favor)
- ✅ **Honour** (not honor)
- ✅ **Labour** (not labor)
- ✅ **Licence** (noun, not license)
- ✅ **Practice** (noun) vs **Practise** (verb)

---

## 🟠 ORANGE LAYER CONTEXT ENGINEERING INTEGRATION

### Cost Layer Development with Contrast Excellence
```python
def build_orange_layer_with_contrast(wb):
    """Build Orange Layer with proper contrast standards"""
    
    # Orange Layer colour scheme with contrast validation
    orange_colours = {
        'orange_dark': PatternFill(start_color="CC6600", end_color="CC6600", fill_type="solid"),
        'orange_medium': PatternFill(start_color="FF8C00", end_color="FF8C00", fill_type="solid"),
        'orange_light': PatternFill(start_color="FFB366", end_color="FFB366", fill_type="solid")
    }
    
    # Text colours for proper contrast
    contrast_text = {
        'white_on_dark_orange': Font(name='Century Gothic', size=11, color="FFFFFF"),
        'black_on_light_orange': Font(name='Century Gothic', size=11, color="000000"),
        'white_header_orange': Font(name='Century Gothic', size=12, bold=True, color="FFFFFF")
    }
    
    # Build cost sheets with SA compliance
    cost_sheets = [
        'Cost_Accommodation',
        'Cost_Restaurant', 
        'Cost_Adventure_Activities',
        'Cost_Training_Programs',
        'Cost_Ancillary'
    ]
    
    for sheet_name in cost_sheets:
        build_cost_sheet_with_contrast(wb, sheet_name, orange_colours, contrast_text)
```

---

## 🇿🇦 SA COMPLIANCE WITH ROBUST ERROR HANDLING

### Automatic SA Market Pattern Integration (Lessons Learnt Enhanced)
```python
def apply_sa_compliance_robust(wb, sheet_name):
    """Apply SA compliance with error handling from lessons learnt"""
    
    ws = wb[sheet_name]
    
    # LESSON: Check all prerequisite values exist
    sa_rates = {
        'minimum_wage': 23.19,  # R per hour
        'uif_rate': 0.02,       # 2% total
        'sdl_rate': 0.01,       # 1% for payrolls over R500k
        'vat_rate': 0.15        # 15%
    }
    
    # Apply minimum wage calculations with proper contrast
    if 'staff' in sheet_name.lower():
        for row in range(10, 30):  # Staff cost rows
            cell_ref = f'C{row}'
            if ws[cell_ref].value and isinstance(ws[cell_ref].value, (int, float)):
                # Ensure minimum wage compliance
                hourly_rate = ws[cell_ref].value / 160  # Monthly to hourly
                if hourly_rate < sa_rates['minimum_wage']:
                    corrected_monthly = sa_rates['minimum_wage'] * 160
                    safe_cell_write(ws, cell_ref, corrected_monthly)
                    # Ensure proper contrast on updated cells
                    ws[cell_ref].font = TEXT_COLOUR_STANDARDS['black_on_light']
```

---

## 🚀 EXECUTION COMMAND WITH SA SPELLING & CONTRAST

**WORKBOOK PATH:** 
`/Users/mac/Downloads/Hostel Diary Financial Model/Hostel_Diary_Financial_Model_V2_HEADERS_FIXED_20250718_200820.xlsx`

**ROBUST PRP EXECUTION SEQUENCE:**

1. **Phase 1 - Context Loading & Validation**
   - Load PRP framework and lessons learnt patterns
   - Validate workbook prerequisites and existing state
   - Initialise robust error handling and logging

2. **Phase 2 - Design Foundation & Contrast Architecture**
   - Create layer reference infrastructure
   - Apply exact design standards (Century Gothic, RGB colours, CONTRAST)
   - Set up progressive calculation framework

3. **Phase 3 - Progressive Sheet Building**
   - Build each sheet using lessons learnt patterns
   - Apply SA compliance with error handling
   - MCP validation after each component
   - **CRITICAL**: Enforce contrast standards on every cell

4. **Phase 4 - Integration & Error Recovery**
   - Create cross-layer linkages with validation
   - Auto-fix common issues from lessons learnt
   - Update master reference architecture

5. **Phase 5 - Quality Assurance & Completion**
   - Comprehensive validation against all standards
   - Generate completion report with metrics
   - Save with backup and documentation

**CRITICAL SUCCESS FACTORS FROM LESSONS LEARNT:**
- ⚠️ **Century Gothic enforcement** - Zero tolerance for font deviation
- ⚠️ **Contrast excellence** - Readable in all lighting conditions and colour-blind friendly
- ⚠️ **SA English spelling** - Colour, centre, realise, analyse throughout
- 🔗 **Reference integrity** - Every reference documented and validated
- 🇿🇦 **SA compliance automation** - Built-in regulatory compliance
- 📊 **Progressive building** - Stage-by-stage dependency management
- ✅ **Three-layer validation** - Python builds, MCP validates, Python fixes

**EXECUTE:** Following the complete PRP methodology enhanced with technical lessons learnt, build the [LAYER NAME] with investment-grade quality, robust error handling, contrast excellence, and comprehensive SA market compliance using proper South African English spelling throughout.

**EXPECTED OUTCOME:** Professional financial model layer built using proven patterns, with zero technical debt, complete reference documentation, excellent contrast for usability, and investment committee presentation readiness with full SA compliance.

---

*This PRP-based prompt integrates comprehensive technical lessons learnt from actual model development, ensuring robust, professional, and error-free financial model construction with SA compliance, contrast excellence, and investment-grade presentation standards using proper South African English spelling.*