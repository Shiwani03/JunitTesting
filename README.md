# JunitTesting
package com.ict100.UnitProject;

public class Calculator {
	public static int add(int number, int number2)
	{
		return number + number2;
	}
public static int sub(int number1, int number2) {
	return number1 - number2;
}
public static int mul(int number1, int number2) {
	return number1*number2;
}
public static double div(double number1, double number2) {
	if(number2 ==0) {
		throw new IllegalArgumentException( "Number cannot be divide by 0!");
	}
	return number1/number2;
}

}

#UnitTest
import static org.junit.Assert.*;

import org.junit.jupiter.api.Test;

import com.ict100.UnitProject.Calculator;

public class UnitTest {

	@Test
	public void unitTest() {
		assertEquals("error in add()", 3, Calculator.add(1, 2));
		assertEquals("error in add()", -3, Calculator.add(-1, -2));
		assertEquals("error in add()", 9, Calculator.add(9, 0));
	}
public void calcTestAFail() {
	assertEquals("error in add()", 0, Calculator.add(1, 2));
}
public void calcTestPass() {
	assertEquals("error in sub()", 1, Calculator.add(1, 2));
	assertEquals("error in sub()", -1, Calculator.add(-1, -2));
	assertEquals("error in sub()", 0, Calculator.add(2, 1));
}
public void calcSubFail() {
	assertEquals("error in add()", 0, Calculator.add(2, 1));
}
}
