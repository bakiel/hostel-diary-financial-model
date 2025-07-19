# 🏨 COMPREHENSIVE UNIVERSAL HOSTEL FINANCIAL MODEL PROMPT

> **Advanced AI-Assisted Financial Model Development Framework**  
> Engineered for robust, SA-compliant hostel financial modelling with technical validation

---

## 🎯 PROJECT OVERVIEW

**OBJECTIVE**: Create a comprehensive, investment-grade financial model for Hostel Diary using proven technical patterns, South African regulatory compliance, and robust validation frameworks.

**CRITICAL SUCCESS FACTORS**:
- ✅ Technical robustness with error recovery patterns
- ✅ SA regulatory compliance (UIF, SDL, VAT, labour law)
- ✅ Design consistency with enforced standards
- ✅ Progressive calculation architecture
- ✅ Comprehensive validation at every layer

---

## 🧠 CONTEXT & BACKGROUND

### Business Context
**Hostel Diary** is a boutique hostel operation targeting the South African hospitality market. The financial model must support:

- **Investment decisions**: ROI analysis, funding requirements
- **Operational planning**: Cash flow management, breakeven analysis  
- **Regulatory compliance**: SA labour law, tax obligations, municipal requirements
- **Stakeholder communication**: Professional presentation to investors/banks
- **Scenario planning**: Sensitivity analysis for different market conditions

### Technical Context  
This model leverages **Context Engineering** - an advanced AI development methodology that combines:
- Proven technical patterns from lessons learned
- Robust validation frameworks
- Progressive Reference Protocol (PRP) architecture
- SA-specific compliance integration

---

## 🎨 CRITICAL DESIGN STANDARDS - NON-NEGOTIABLE

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

### COLOUR STANDARDS (EXACT RGB FROM LESSONS LEARNED)
```python
# LESSON: Use exact RGB values to avoid colour detection issues
COLOUR_STANDARDS = {
    'yellow_input': PatternFill(start_color="FFFF00", end_color="FFFF00", fill_type="solid"),
    'blue_calculation': PatternFill(start_color="BDD7EE", end_color="BDD7EE", fill_type="solid"),
    'green_output': PatternFill(start_color="C6E0B4", end_color="C6E0B4", fill_type="solid"),
    'orange_costs': PatternFill(start_color="FFA500", end_color="FFA500", fill_type="solid"),
    'navy_summary': PatternFill(start_color="002060", end_color="002060", fill_type="solid"),
    'white_base': PatternFill(start_color="FFFFFF", end_color="FFFFFF", fill_type="solid")
}
```

### SOUTH AFRICAN ENGLISH REQUIREMENTS
**MANDATORY SPELLING STANDARDS:**
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

---

## 🏗️ TECHNICAL ARCHITECTURE (FROM LESSONS LEARNED)

### THREE-LAYER VALIDATION FRAMEWORK
```python
# LESSON: Build error recovery, not just error detection
# Layer 1: Python Creates (with safe patterns)
# Layer 2: MCP Validates (comprehensive checking)  
# Layer 3: Python Fixes (auto-recovery)

def three_layer_validation():
    """Implement robust validation with auto-recovery"""
    try:
        # Layer 1: Create with safe patterns
        result = create_with_safe_patterns()
        
        # Layer 2: Comprehensive validation
        validation_result = mcp_validate_comprehensive(result)
        
        if not validation_result.passed:
            # Layer 3: Auto-recovery
            fixed_result = python_auto_fix(result, validation_result.errors)
            return fixed_result
            
        return result
    except Exception as e:
        return handle_critical_failure(e)
```

### PROGRESSIVE CALCULATION PATTERN
```python
# LESSON: Build dependencies in stages to prevent cascade failures
# Stage 1: Base values from assumptions (validate sources exist)
# Stage 2: Monthly calculations (depends on Stage 1)
# Stage 3: Annual totals (depends on Stage 2)  
# Stage 4: Projections (depends on Stage 3)

def progressive_calculation_pattern():
    """Implement staged calculations with dependency validation"""
    
    # Stage 1: Validate base assumptions exist
    base_assumptions = validate_base_assumptions()
    if not base_assumptions.valid:
        raise ValueError(f"Base assumptions missing: {base_assumptions.missing}")
    
    # Stage 2: Monthly calculations
    monthly_calcs = calculate_monthly_values(base_assumptions)
    validate_monthly_calculations(monthly_calcs)
    
    # Stage 3: Annual aggregation  
    annual_totals = aggregate_to_annual(monthly_calcs)
    validate_annual_totals(annual_totals)
    
    # Stage 4: Multi-year projections
    projections = create_projections(annual_totals)
    validate_projections(projections)
    
    return {
        'base': base_assumptions,
        'monthly': monthly_calcs,
        'annual': annual_totals,
        'projections': projections
    }
```

---

## 🇿🇦 SOUTH AFRICAN COMPLIANCE FRAMEWORK

### LABOUR LAW COMPLIANCE
```python
# MANDATORY: SA labour law compliance patterns
SA_LABOUR_STANDARDS = {
    'minimum_wage_2024': 23.19,  # R23.19 per hour
    'overtime_rate': 1.5,        # 1.5x normal rate
    'annual_leave_days': 21,     # 21 working days minimum
    'sick_leave_days': 30,       # 30 days per 3-year cycle
    'maternity_leave_days': 120, # 4 months maternity leave
    'uif_rate': 0.02,           # 2% (1% employer + 1% employee)
    'sdl_rate': 0.01,           # 1% Skills Development Levy
    'maximum_working_hours': 45  # 45 hours per week
}

def apply_sa_labour_compliance(salary_data):
    """Apply SA labour law compliance to salary calculations"""
    for employee in salary_data:
        # Minimum wage enforcement
        hourly_rate = employee['monthly_salary'] / (4.33 * SA_LABOUR_STANDARDS['maximum_working_hours'])
        if hourly_rate < SA_LABOUR_STANDARDS['minimum_wage_2024']:
            raise ValueError(f"Salary below minimum wage: {employee['name']}")
        
        # Calculate UIF contributions
        employee['uif_employee'] = min(employee['monthly_salary'] * 0.01, 148.26)  # Monthly ceiling
        employee['uif_employer'] = employee['uif_employee']  # Employer matches
        
        # Calculate SDL
        employee['sdl'] = employee['monthly_salary'] * SA_LABOUR_STANDARDS['sdl_rate']
        
        # Add leave provisions
        employee['leave_provision'] = employee['monthly_salary'] * (21/251)  # 21 days per working year
    
    return salary_data
```

---

## 🟠 COST LAYER DEVELOPMENT (ORANGE LAYER)

### COST CATEGORY STRUCTURE
```python
COST_CATEGORIES = {
    'labour': {
        'colour': COLOUR_STANDARDS['orange_costs'],
        'subcategories': ['management', 'operations', 'housekeeping', 'security'],
        'sa_compliance': ['minimum_wage', 'uif', 'sdl', 'leave_provision']
    },
    'utilities': {
        'colour': COLOUR_STANDARDS['orange_costs'],
        'subcategories': ['electricity', 'water', 'gas', 'telecommunications'],
        'sa_specific': ['eskom_tariffs', 'municipal_rates', 'water_restrictions']
    },
    'supplies': {
        'colour': COLOUR_STANDARDS['orange_costs'],
        'subcategories': ['consumables', 'linen', 'cleaning', 'maintenance'],
        'calculation_method': 'per_occupied_room_night'
    },
    'compliance': {
        'colour': COLOUR_STANDARDS['orange_costs'],
        'subcategories': ['licences', 'permits', 'insurance', 'professional_fees'],
        'sa_specific': ['tourism_licence', 'fire_certificate', 'health_permit']
    }
}
```

### GIT WORKFLOW FOR COST LAYER
```bash
# Cost layer specific git workflow
git checkout -b feature/cost-layer-foundation

# Progressive cost development commits
git commit -m "cost(foundation): establish orange cost layer architecture

- Orange colour scheme (#FFA500) implementation
- Progressive calculation framework
- SA tax compliance foundation  
- Reference architecture for cost dependencies"

git commit -m "cost(labour): implement SA minimum wage compliance

- Base rate: R23.19/hour (2024 minimum wage)
- UIF: 2% (1% employer + 1% employee)
- SDL: 1% of gross wages
- Validation: prevents below-minimum wage entries
- Impact: ensures full labour law compliance

Refs: Labour Relations Act compliance"

git commit -m "cost(utilities): add Eskom tariff structure

- Residential tariff: R1.85/kWh
- Business tariff: R2.15/kWh  
- Demand charges: R150/kVA
- Municipal rates: 15% markup
- Impact: accurate utility cost projections

Source: Eskom 2024 tariff schedule"
```

---

## 🚀 EXECUTION COMMAND

**EXECUTE THIS COMPREHENSIVE FRAMEWORK NOW**

Using the technical patterns, SA compliance requirements, and validation frameworks specified above:

1. **Implement Phase 1**: Load context with validation
2. **Implement Phase 2**: Establish design foundation with Century Gothic enforcement
3. **Implement Phase 3**: Build sheets progressively with orange cost layer
4. **Implement Phase 4**: Integrate with comprehensive validation
5. **Implement Phase 5**: Final quality assurance and delivery

**SUCCESS CRITERIA**: Delivery of investment-grade hostel financial model with complete SA compliance, technical robustness, and professional design standards.

**FAILURE CONDITIONS**: Any deviation from Century Gothic font, colour standards, SA compliance requirements, or technical validation patterns constitutes immediate failure.

---

*This prompt represents the culmination of Context Engineering methodology - a battle-tested framework for AI-assisted financial model development.*