# StringReverse
Creat by: Денси Казанцев Артем Николаев

-lib

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    
    namespace StringReverseLibrary
    {
        public class StringReversClass
        {
            public static string ReverseString(string textString)
            {
                char[] chars = textString.ToCharArray();
                Array.Reverse(chars);
                if (String.IsNullOrEmpty(textString))
                {
                    throw new Exception("Пустота)");
                }
                return new string(chars).ToLower();
            }
        }
    }
-test

    using Microsoft.VisualStudio.TestTools.UnitTesting;
    using System;
    using StringReverseLibrary;
    namespace StringReverseLibrarytTest
    {
        [TestClass]
        public class Revers
        {
            [TestMethod]
            public void Revers_1()
            {
                string textString = "Привет!";
                string expected = "!тевирп";
                string actual = StringReversClass.ReverseString(textString);
                Assert.AreEqual(expected, actual);
            }
            [TestMethod]
            public void Revers_Exeption()
            {
                string textString = "";
                Action actual = () => StringReversClass.ReverseString(textString);
                Assert.ThrowsException<Exception>(actual);
            }
            [TestMethod]
            public void Revers_2()
            {
                string textString = "qwerty";
                string expected = "ytrewq";
                string actual = StringReversClass.ReverseString(textString);
                Assert.AreEqual(expected, actual);
            }
            [TestMethod]
            public void Revers_3()
            {
                string textString = "Qwerty";
                string expected = "ytrewq";
                string actual = StringReversClass.ReverseString(textString);
                Assert.AreEqual(expected, actual);
            }
        }
    }
