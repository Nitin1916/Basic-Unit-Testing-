# Basic-Unit-Testing-
Creating a project containing arithmetic operations then importing it in original project .With use of unittest library executing the programfor 

def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

import unittest
from project import add, subtract, multiply, divide

class TestCalculator(unittest.TestCase):

    def test_add_positive(self):
        self.assertEqual(add(2, 3), 5)

    def test_add_negative(self):
        self.assertEqual(add(-2, -3), -5)

    def test_subtract_positive(self):
        self.assertEqual(subtract(10, 5), 5)

    def test_subtract_negative(self):
        self.assertEqual(subtract(-10, -5), -5)

    def test_multiply_positive(self):
        self.assertEqual(multiply(4, 5), 20)

    def test_multiply_zero(self):
        self.assertEqual(multiply(4, 0), 0)

    def test_divide_positive(self):
        self.assertEqual(divide(10, 2), 5)

    def test_divide_float(self):
        self.assertEqual(divide(5, 2), 2.5)

    def test_divide_by_zero(self):
        with self.assertRaises(ValueError):
            divide(5, 0)

    def test_add_zero(self):
        self.assertEqual(add(0, 0), 0)

if __name__ == "__main__":
    unittest.main()
