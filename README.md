# balshak.T
python code PAYROLL MANAGEMENT SYSTEM
class Employee:
    def __init__(self, emp_id, name, designation, salary):
        self.emp_id = emp_id
        self.name = name
        self.designation = designation
        self.salary = salary

class PayrollSystem:
    def __init__(self):
        self.employees = []

    def add_employee(self, employee):
        self.employees.append(employee)

    def calculate_payroll(self):
        print("Payroll Calculations:")
        print("====================")
        for employee in self.employees:
            print(f"{employee.name} - {employee.designation}: ${employee.salary}")
djanco code 
# views.py
from django.shortcuts import render
from .models import Employee

def employee_list(request):
    employees = Employee.objects.all()
    return render(request, 'payroll/employee_list.html', {'employees': employees})

def calculate_payroll(request):
    employees = Employee.objects.all()
    total_salary = sum(employee.salary for employee in employees)
    return render(request, 'payroll/payroll_summary.html', {'total_salary': total_salary})

