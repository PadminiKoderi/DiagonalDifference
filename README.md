# DiagonalDifference
//https://www.hackerrank.com/challenges/diagonal-difference
//Given a square matrix of size N X N, calculate the absolute difference between the sums of its diagonals.
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
class Solution {

    static void Main(String[] args) 
    {
        int n = Convert.ToInt32(Console.ReadLine());
        int[][] a = new int[n][];
        int primaryDia=0,secDia=0,secDiaTemp=0;
        for(int a_i = 0; a_i < n; a_i++){
           string[] a_temp = Console.ReadLine().Split(' ');
           a[a_i] = Array.ConvertAll(a_temp,Int32.Parse);
        }
        for(int i=0;i<=(n-1);i++){
                primaryDia=a[i][i]+primaryDia;
                for(int j=(n-1);j<=n;j--)
                {
                    secDiaTemp=a[i][j];
                    if(i==(n-1)-j)
                        break;
                }
                secDia=secDiaTemp+secDia;
        }
        Console.WriteLine(Math.Abs(primaryDia-secDia));
    }
}

