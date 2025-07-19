# 🇿🇦 South African Compliance Guide

> Comprehensive regulatory framework for hostel financial modelling

## 📋 Labour Relations Act Compliance

### Minimum Wage Requirements (2024)
```python
MINIMUM_WAGE_2024 = {
    'general': 23.19,           # R23.19 per hour
    'farm_workers': 20.76,      # R20.76 per hour
    'domestic_workers': 19.09,   # R19.09 per hour
    'expanded_public_works': 12.75  # R12.75 per hour
}

# Hostel workers fall under 'general' category
HOSTEL_MINIMUM_WAGE = 23.19  # R23.19 per hour
```

### Working Time Regulations
```python
WORKING_TIME_LIMITS = {
    'ordinary_hours_per_week': 45,
    'ordinary_hours_per_day': 9,
    'overtime_threshold': 45,
    'overtime_rate_multiplier': 1.5,
    'sunday_work_rate': 2.0,
    'public_holiday_rate': 2.0
}
```

### Leave Entitlements
```python
LEAVE_ENTITLEMENTS = {
    'annual_leave_days': 21,        # 21 consecutive days per year
    'sick_leave_cycle_days': 30,    # 30 days per 36-month cycle
    'maternity_leave_days': 120,    # 4 consecutive months
    'family_responsibility_days': 3  # 3 days per year
}
```

### UIF (Unemployment Insurance Fund)
```python
UIF_PARAMETERS = {
    'employee_contribution_rate': 0.01,  # 1% of gross salary
    'employer_contribution_rate': 0.01,  # 1% of gross salary
    'total_contribution_rate': 0.02,     # 2% total
    'monthly_salary_ceiling': 14810,     # R14,810 per month
    'annual_salary_ceiling': 177720,     # R177,720 per year
    'monthly_contribution_ceiling': 148.10  # R148.10 per month
}

# UIF Calculation Function
def calculate_uif(monthly_salary):
    capped_salary = min(monthly_salary, UIF_PARAMETERS['monthly_salary_ceiling'])
    employee_uif = capped_salary * UIF_PARAMETERS['employee_contribution_rate']
    employer_uif = capped_salary * UIF_PARAMETERS['employer_contribution_rate']
    
    return {
        'employee_contribution': employee_uif,
        'employer_contribution': employer_uif,
        'total_contribution': employee_uif + employer_uif
    }
```

### SDL (Skills Development Levy)
```python
SDL_PARAMETERS = {
    'levy_rate': 0.01,              # 1% of gross payroll
    'annual_payroll_threshold': 500000,  # R500,000 per year
    'exemption_threshold': 500000   # Exempt if payroll < R500,000
}

# SDL Calculation Function
def calculate_sdl(annual_payroll):
    if annual_payroll < SDL_PARAMETERS['annual_payroll_threshold']:
        return 0
    
    return annual_payroll * SDL_PARAMETERS['levy_rate']
```

## 💰 Tax Compliance

### VAT (Value-Added Tax)
```python
VAT_PARAMETERS = {
    'standard_rate': 0.15,          # 15% standard rate
    'zero_rate': 0.00,              # 0% for certain supplies
    'registration_threshold': 1000000,  # R1,000,000 annual turnover
    'deregistration_threshold': 300000  # R300,000 annual turnover
}

# VAT Calculation Function
def calculate_vat(revenue_amount, vat_inclusive=True):
    if vat_inclusive:
        vat_amount = revenue_amount * (VAT_PARAMETERS['standard_rate'] / (1 + VAT_PARAMETERS['standard_rate']))
        net_amount = revenue_amount - vat_amount
    else:
        vat_amount = revenue_amount * VAT_PARAMETERS['standard_rate']
        net_amount = revenue_amount
    
    return {
        'net_amount': net_amount,
        'vat_amount': vat_amount,
        'gross_amount': net_amount + vat_amount
    }
```

### Company Income Tax
```python
COMPANY_TAX_PARAMETERS = {
    'standard_rate': 0.27,          # 27% for companies
    'small_business_rate': 0.28,    # 28% for close corporations
    'turnover_tax_threshold': 20000000  # R20,000,000 annual turnover
}

# Turnover Tax Rates (Alternative for small businesses)
TURNOVER_TAX_RATES = {
    (0, 335000): 0.00,              # 0% on first R335,000
    (335001, 500000): 0.01,         # 1% on R335,001 - R500,000
    (500001, 750000): 0.02,         # 2% on R500,001 - R750,000
    (750001, 1000000): 0.04,        # 4% on R750,001 - R1,000,000
    (1000001, 1500000): 0.06,       # 6% on R1,000,001 - R1,500,000
    (1500001, 20000000): 0.08       # 8% on R1,500,001 - R20,000,000
}
```

### PAYE (Pay As You Earn)
```python
PAYE_TAX_BRACKETS_2024 = [
    (0, 95750, 0.18, 0),
    (95751, 237100, 0.26, 17235),
    (237101, 370500, 0.31, 54648),
    (370501, 512800, 0.36, 95341),
    (512801, 673000, 0.39, 146569),
    (673001, 857900, 0.41, 208947),
    (857901, float('inf'), 0.45, 284706)
]

# PAYE Calculation Function
def calculate_paye(annual_salary):
    for min_income, max_income, rate, rebate in PAYE_TAX_BRACKETS_2024:
        if min_income <= annual_salary <= max_income:
            tax_before_rebate = (annual_salary - min_income) * rate + rebate
            # Primary rebate for 2024: R17,235
            tax_after_rebate = max(0, tax_before_rebate - 17235)
            return tax_after_rebate
    return 0
```

## 🏨 Tourism Industry Compliance

### Tourism Business Act Requirements
```python
TOURISM_COMPLIANCE = {
    'grading_required': True,       # Grading certificate required
    'licence_required': True,       # Tourism business licence
    'registration_threshold': 0,    # All tourism businesses must register
    'renewal_period_months': 12     # Annual renewal
}
```

### Health and Safety Regulations
```python
HEALTH_SAFETY_REQUIREMENTS = {
    'fire_certificate': True,       # Fire safety certificate
    'health_certificate': True,     # Health certificate
    'occupancy_certificate': True,  # Occupancy certificate
    'liquor_licence': False,        # Optional for hostels
    'food_handlers_permits': True   # If serving food
}
```

## 🏛️ Municipal Compliance

### Rates and Taxes
```python
MUNICIPAL_RATES = {
    'property_rates_percentage': 0.015,  # Typically 1.5% of property value
    'refuse_removal_monthly': 350,      # Average monthly refuse fee
    'sewerage_monthly': 280,            # Average monthly sewerage fee
    'water_basic_monthly': 200,         # Basic water charge
    'electricity_basic_monthly': 150    # Basic electricity connection
}
```

### Business Licence Requirements
```python
BUSINESS_LICENCE_REQUIREMENTS = {
    'business_licence': True,           # Municipal business licence
    'zoning_compliance': True,          # Zoning certificate
    'building_plans_approval': True,    # Building plans approved
    'environmental_clearance': False,   # May be required for larger operations
    'noise_permit': False              # May be required in residential areas
}
```

## 📊 Financial Reporting Compliance

### Companies Act Requirements
```python
COMPANIES_ACT_COMPLIANCE = {
    'annual_financial_statements': True,  # Required for all companies
    'audit_threshold_revenue': 10000000,  # R10m public interest score
    'independent_review_threshold': 2000000,  # R2m revenue threshold
    'filing_deadline_months': 6          # 6 months after year-end
}
```

### CIPC (Companies and Intellectual Property Commission)
```python
CIPC_REQUIREMENTS = {
    'annual_return_filing': True,       # Annual return required
    'company_registration': True,       # Company must be registered
    'director_changes_notification': True,  # Notify director changes
    'address_changes_notification': True   # Notify address changes
}
```

## 🛡️ Compliance Validation Framework

### Automated Compliance Checker
```python
class SAComplianceChecker:
    def __init__(self):
        self.violations = []
    
    def check_labour_compliance(self, employee_data):
        for employee in employee_data:
            # Check minimum wage
            hourly_rate = self.calculate_hourly_rate(employee['monthly_salary'])
            if hourly_rate < HOSTEL_MINIMUM_WAGE:
                self.violations.append(f"Minimum wage violation: {employee['name']}")
            
            # Check UIF compliance
            uif = calculate_uif(employee['monthly_salary'])
            if not uif:
                self.violations.append(f"UIF calculation missing: {employee['name']}")
        
        return len(self.violations) == 0
    
    def generate_compliance_report(self):
        if not self.violations:
            return "✅ All compliance requirements met"
        
        report = "⚠️ Compliance Issues Found:\n"
        for i, violation in enumerate(self.violations, 1):
            report += f"{i}. {violation}\n"
        
        return report
```

## 📅 Compliance Calendar

### Key Dates and Deadlines
```python
COMPLIANCE_CALENDAR = {
    'monthly': {
        'vat_return': 'Last working day of the month',
        'paye_payment': '7th of following month',
        'uif_payment': '7th of following month',
        'sdl_payment': '7th of following month'
    },
    'quarterly': {
        'provisional_tax': 'Last day of 4th, 8th, and 12th months'
    },
    'annually': {
        'income_tax_return': '31 October (companies)',
        'annual_financial_statements': '6 months after year-end',
        'cipc_annual_return': 'Anniversary of registration',
        'tourism_licence_renewal': 'Licence expiry date'
    }
}
```

## ⚖️ Legal References

### Key Legislation
```python
LEGAL_REFERENCES = {
    'labour': {
        'basic_conditions_of_employment_act': 'Act 75 of 1997',
        'labour_relations_act': 'Act 66 of 1995',
        'employment_equity_act': 'Act 55 of 1998',
        'skills_development_act': 'Act 97 of 1998'
    },
    'tax': {
        'income_tax_act': 'Act 58 of 1962',
        'value_added_tax_act': 'Act 89 of 1991',
        'unemployment_insurance_act': 'Act 63 of 2001'
    },
    'tourism': {
        'tourism_act': 'Act 3 of 2014',
        'consumer_protection_act': 'Act 68 of 2008'
    },
    'municipal': {
        'municipal_systems_act': 'Act 32 of 2000',
        'municipal_property_rates_act': 'Act 6 of 2004'
    }
}
```

This compliance framework ensures that all hostel financial models meet South African regulatory requirements and can be confidently presented to investors, banks, and regulatory authorities.