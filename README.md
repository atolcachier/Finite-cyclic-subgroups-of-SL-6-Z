# Finite-subgroups-of-SL-6-Z- 
Written to be used in GAP
Download cryst6 from https://drive.google.com/drive/u/1/folders/1E8PKEZ6mAM9oCUyJt-A7u76fJdZE3trH and copy all the text from the .txt in GAP (I extracted the .txt's from https://www.math.kyoto-u.ac.jp/~yamasaki/Algorithm/RatProbAlgTori/crystdat.html and gave them a format to be copied in GAP without changes)

We check the cyclic subgroups of matrices with determinant equal to one:

for i in [1..85308] do if IsCyclic(Group(cryst6[i]))=true and Determinant(GeneratorsOfGroup(Group(cryst6[i]))[1])=1 then Print(i, " "); fi; od;

One obtain the following indexes:
7 8 9 10 11 12 109 110 189 190 191 192 193 194 195 196 197 198 199 200 10790
10791 10792 10793 10794 10795 10796 10797 13925 13926 16827 16828 16830 16831
16832 16833 16834 16835 16836 16837 16858 16859 16886 16887 16888 16889 16902
16903 16904 16905 16912 16913 17162 17163 17164 17165 17166 17167 17168 17169
17170 17171 17172 17173 37745 37746 38597 38601 38636 38640 38656 38657 38658
38659 38675 38676 38762 38763 38816 38818 38819 38820 40067 40068 40104 40105
40127 40128 40129 40130 49200 49201 49202 49203 49204 49205 49206 49746 49747
49748 49749 50083 50084 50085 50086 50087 50088 50089 50090 50091 50092 50093
50094 50095 74945 74946 74947 74948 75126 75127 75128 75130 75131

Then we put

conj6:=cryst6{[7,8,9,10,11,12,109,110,189,190,191,192,193,194,195,196,197,198,199,200,10790,10791,10792,10793,10794,10795,10796,10797,13925,13926,16827,16828,16830,16831,16832,16833,16834,16835,16836,16837,16858,16859,16886,16887,16888,16889,16902,16903,16904,16905,16912,16913,17162,17163,17164,17165,17166,17167,17168,17169,17170,17171,17172,17173,37745,37746,38597,38601,38636,38640,38656,38657,38658,38659,38675,38676,38762,38763,38816,38818,38819,38820,40067,40068,40104,40105,40127,40128,40129,40130,49200,49201,49202,49203,49204,49205,49206,49746,49747,49748,49749,50083,50084,50085,50086,50087,50088,50089,50090,50091,50092,50093,50094,50095,74945,74946,74947,74948,75126,75127,75128,75130,75131]};;

and we compute 

Size(conj6);

and it gives 123.

Explicitly, the 123 subgroups are:

conj6:=[ [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ] ] ]
    ,
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ]
     ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, -1 ],
          [ 0, 0, 1, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 0 ] ]
     ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, -1 ],
          [ 0, 0, 1, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 0 ] ]
     ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, -1, -1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 1 ], [ 0, 0, 0, 0, -1, 1 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, -1, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ],
          [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 0 ]
         ] ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 1, 1, 0, 0, 0 ],
          [ 0, 0, 0, -1, -1, 0 ], [ 0, 0, 0, 1, 0, 1 ], [ 0, 0, 0, 1, 0, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 1, 1 ], [ 0, 1, 0, -1, -1, 1 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ] ]
     ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 1, 1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 1 ], [ 0, 0, 0, 0, -1, 1 ]
         ] ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, -1, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, -1, 0 ], [ 0, 0, 0, 1, 0, 1 ], [ 0, 0, 0, 1, 0, 0 ]
         ] ],
  [ [ [ 1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 1, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 1, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, -1, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, -1 ], [ 0, 1, -1, 0, 0, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 1, -1, 0, 0 ], [ 0, 0, 1, 0, 1, 0 ]
         ] ],
  [ [ [ -1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 1, 0, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 1, -1, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 1, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 1 ], [ 0, -1, 1, 0, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, -1, 1, 0, 0 ], [ 0, 0, -1, 0, -1, 0 ]
         ] ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, -1, -1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 1, 0, 1, 0 ] ]
     ],
  [ [ [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 1, -1, 0, 0, 0 ],
          [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 1, -1, 0 ],
          [ -1, 0, 0, 0, 0, -1 ] ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 1, 0, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 1 ]
         ] ],
  [ [ [ -1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, -1, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ]
         ] ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, -1, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ],
          [ 0, 0, 0, 0, 0, -1 ] ] ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ -1, 1, 0, 0, 0, 0 ], [ 0, 0, 1, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 1, -1, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ] ]
     ],
  [ [ [ 0, 0, 0, 0, 1, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 1, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ -1, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, -1, -1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, -1 ]
         ] ],
  [ [ [ 1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, -1, 0 ]
         ] ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 1, 0, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 1 ]
         ] ],
  [ [ [ -1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 1, 0 ]
         ] ],
  [ [ [ -1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ 1, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ -1, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, -1, 1, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ -1, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 0, 1, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ],
          [ 0, 0, -1, -1, 0, 0 ] ] ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 0, 1, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ],
          [ 0, 0, -1, -1, 0, 0 ] ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ]
     ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, -1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 1, 0, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ],
          [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, -1, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 1, 1, 0, 0 ] ]
     ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, -1, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 1, 1, 0, 0 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ 0, 0, 0, 0, -1, -1 ], [ 0, 0, 0, 0, 0, 1 ], [ 1, 1, 0, 0, 0, 0 ],
          [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 1, 0, 0, 0, 0, 0 ],
          [ 0, 0, 1, 0, 0, -1 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 1, 0, 0, 0, -1, 0 ], [ 1, 0, -1, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ],
          [ -1, 1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 1 ], [ -1, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 1, 0 ], [ -1, 0, 1, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ],
          [ 1, -1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, -1 ], [ 1, 0, 0, 1, 0, 0 ]
         ] ],
  [ [ [ 0, 1, -1, 0, 0, 0 ], [ 0, 1, 0, -1, 0, 0 ], [ 1, 0, 0, -1, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ 0, 0, 0, -1, 0, 0 ], [ 1, 0, 0, -1, 0, 0 ], [ 0, 1, 0, -1, 0, 0 ],
          [ 0, 0, 1, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ 0, 0, 1, -1, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ -1, 0, 1, 0, 0, 0 ],
          [ 0, -1, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ]
     ],
  [ [ [ 0, 1, -1, 0, 0, 0 ], [ 0, -1, 1, -1, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, 1 ],
          [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ] ]
     ],
  [ [ [ 1, -1, 0, 0, 0, 0 ], [ 1, 0, -1, 0, 0, 0 ], [ 1, 0, 0, -1, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 0 ] ]
     ],
  [ [ [ -1, 1, 0, 0, 0, 0 ], [ -1, 0, 1, 0, 0, 0 ], [ -1, 0, 0, 1, 0, 0 ],
          [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 0, 0, -1, 1, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 1, 0, -1, 0, 0, 0 ],
          [ 0, 1, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, -1 ]
         ] ],
  [ [ [ 0, 0, 1, -1, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ -1, 0, 1, 0, 0, 0 ],
          [ 0, -1, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, -1 ]
         ] ],
  [ [ [ 0, 0, 1, -1, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ -1, 0, 1, 0, 0, 0 ],
          [ 0, -1, 1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 1 ]
         ] ],
  [ [ [ 0, 0, -1, 1, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 1, 0, -1, 0, 0, 0 ],
          [ 0, 1, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 1 ]
         ] ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 1, 1, -1, 0, 0 ], [ 1, 0, 1, 0, 0, 0 ],
          [ 1, 0, 1, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 1, 1, -1, 0, 0 ], [ 1, 0, 1, 0, 0, 0 ],
          [ 1, 0, 1, -1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ]
     ],
  [ [ [ -1, -1, 0, 0, 0, 0 ], [ 1, 1, 1, -1, 0, 0 ], [ 1, 0, 1, 0, 0, 0 ],
          [ 1, 0, 1, -1, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ],
  [ [ [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, 1 ],
          [ 0, 1, 0, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 1, -1, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ],
          [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, -1 ]
         ] ],
  [ [ [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 1, 0, 0, -1 ], [ -1, 0, 0, 0, 1, 0 ],
          [ 0, -1, 0, 0, 0, 1 ], [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 1, -1 ]
         ] ],
  [ [ [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, -1, 1, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ],
          [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, -1, 1 ] ]
     ],
  [ [ [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, -1, 0, 0, 1 ], [ 1, 0, 0, 0, -1, 0 ],
          [ 0, 1, 0, 0, 0, -1 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 1 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, -1, 0 ],
          [ 0, 0, 1, 0, 0, 1 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 1, 0, 0 ], [ -1, 0, -1, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 1, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ],
  [ [ [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, -1, 0, 0, 0, -1 ],
          [ 1, 0, 0, 0, 1, 0 ], [ 0, 0, 0, -1, -1, 0 ], [ 0, 0, 1, 0, 0, -1 ]
         ] ],
  [ [ [ 0, -1, 0, -1, 0, 0 ], [ 1, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, -1, 0, 1 ], [ 0, 0, 0, 0, -1, 0 ]
         ] ],
  [ [ [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 1, 0, 0, 0, 1 ],
          [ -1, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 1, 1, 0 ], [ 0, 0, -1, 0, 0, 1 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, -1, 0, -1 ], [ 0, 0, 0, 0, 1, -1 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 1, 0 ], [ 0, 0, 0, -1, 0, -1 ], [ 0, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, 1, 1, 0 ], [ 0, 0, 0, -1, 0, -1 ], [ 0, 0, 0, -1, 0, 0 ]
         ] ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ],
          [ 0, 0, 0, -1, -1, 0 ], [ 0, 0, 0, 1, 0, 1 ], [ 0, 0, 0, 1, 0, 0 ]
         ] ],
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ],
          [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, 1, 0 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 1 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 1, 0, 1, 0 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, -1, 0, -1, -1 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ],
          [ 0, 1, 0, 0, 0, 1 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 1 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, -1, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ],
          [ 0, 1, 0, 0, 1, 0 ], [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ] ] ]
    ,
  [ [ [ 0, -1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ],
          [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ] ] ]
    ,
  [ [ [ 0, 0, 0, -1, 0, 1 ], [ -1, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ],
          [ 0, 0, 0, 1, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ 0, 1, 0, 1, 0, -1 ] ]
     ],
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, -1, 0, 0, 0 ] ]
     ],
  [ [ [ 0, 0, 1, 0, 0, 0 ], [ 0, 0, 0, -1, 1, -1 ], [ 1, 0, 0, 0, 0, 0 ],
          [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, 0, 0, 1, 0 ] ] ]
    ,
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, -1, 0, 0 ],
          [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ], [ 0, 0, -1, 0, 0, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, 0 ], [ 0, 0, 0, 0, 0, -1 ]
         ] ],
  [ [ [ -1, 0, 0, 0, 0, 0 ], [ 0, 0, -1, -1, 0, 1 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, 0, -1, 0 ], [ 0, -1, 0, 0, 0, -1 ],
          [ 0, 0, 0, 1, 0, -1 ] ] ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 0 ], [ 0, 0, 0, 0, 0, 1 ] ] ]
    ,
  [ [ [ 1, 0, 0, 0, 0, 0 ], [ 0, 1, 0, 0, 1, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 0, 0, 0, 0, -1, 0 ], [ 0, -1, 0, 0, 0, -1 ],
          [ 0, -1, -1, 0, -1, 0 ] ] ],
  [ [ [ 0, 0, 0, -1, 0, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ -1, 0, 0, 0, 0, 0 ],
          [ 0, -1, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 0, -1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ],
  [ [ [ -1, 0, -1, 0, -1, 0 ], [ 0, 0, 1, 0, 0, 0 ], [ 1, 0, 0, 0, 0, 1 ],
          [ 0, -1, 0, 0, 0, 0 ], [ 1, 1, 1, 1, 1, -1 ], [ 1, 0, 1, 1, 1, 0 ]
         ] ],
  [ [ [ 0, 0, 1, 1, 0, 0 ], [ 0, 0, -1, 0, 0, -1 ], [ 0, -1, 0, 0, 1, 0 ],
          [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 1, 1, 0, 0, 0, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, 1, 1 ], [ 0, 0, 0, 0, -1, 0 ] ]
     ],
  [ [ [ 0, 1, 0, 0, 0, 0 ], [ 0, 0, -1, 0, 0, 0 ], [ 0, 0, 0, 1, 0, 0 ],
          [ 1, 0, 0, 0, 0, 0 ], [ 0, 0, 0, 0, -1, -1 ], [ 0, 0, 0, 0, 1, 0 ]
         ] ] ];;

Checking that the corresponding lattices are non-isomorphic.
First, we construct the lattices G[i]:=Z \ltimes_{conj[i][1]} \Z^6, for 1<= i<= 123:

F:=FreeGroup("a","b","c","d","e","f","t");
AssignGeneratorVariables(F);
A:=[];
for i in [1..123] do
A[i]:=conj6[i][1]^-1;
od;
G:=[];
for i in [1..123] do
G[i]:=F/[Comm(a,b),Comm(a,c), Comm(a,d),Comm(a,e),Comm(a,f),Comm(b,c),Comm(b,d),Comm(b,e),Comm(b,f),Comm(c,d),Comm(c,e),Comm(c,f),Comm(d,e),Comm(d,f),Comm(e,f),
a^t*(a^A[i][1,1]*b^A[i][2,1]*c^A[i][3,1]*d^A[i][4,1]*e^A[i][5,1]*f^A[i][6,1])^-1, 
b^t*(a^A[i][1,2]*b^A[i][2,2]*c^A[i][3,2]*d^A[i][4,2]*e^A[i][5,2]*f^A[i][6,2])^-1, 
c^t*(a^A[i][1,3]*b^A[i][2,3]*c^A[i][3,3]*d^A[i][4,3]*e^A[i][5,3]*f^A[i][6,3])^-1, 
d^t*(a^A[i][1,4]*b^A[i][2,4]*c^A[i][3,4]*d^A[i][4,4]*e^A[i][5,4]*f^A[i][6,4])^-1, 
e^t*(a^A[i][1,5]*b^A[i][2,5]*c^A[i][3,5]*d^A[i][4,5]*e^A[i][5,5]*f^A[i][6,5])^-1,   
f^t*(a^A[i][1,6]*b^A[i][2,6]*c^A[i][3,6]*d^A[i][4,6]*e^A[i][5,6]*f^A[i][6,6])^-1];
od;

To distinguish them we do the following:

for i in [1..123] do Print(Size(LowIndexSubgroupsFpGroup(G[i],7)), " ");od;

Obtaining 25051 13947 8907 12151 6039 3495 105 120 874 478 442 262 375 203 222 122 471 283 282 158 284 248 176 140 548 512 305 269 70 50 262 223 1160 512 296 296 380 476 233 152 82 110 118 70 127 79 15948 8172 2604 8325 5061 2388 1485 853 1080 569 592 380 2052 1132 1080 704 592 380 307615 77491 10 13 8 14 116 91 96 236 360 235 22 26 23 19 16 20 102 246 44 26 32 20 29 17 433 559 279 171 931 491 303 4517 2421 13101 8189 2345 1145 1209 1145 1081 1081 641 673 673 609 577 609 373 199 107 419 247 57 41 27 29 36.

We put indexes:=[25051,13947,8907,12151,6039,3495,105,120,874,478,442,262,375,203,222,122,471,283,282,158,284,248,176,140,548,512,305,269,70,50,262,223,1160,512,296,296, 380,476,233,152,82,110,118,70,127,79,15948,8172,2604,8325,5061,2388,1485,853,1080,569,592,380,2052,1132,1080,704,592,380,307615,77491,10,13,8,14,116,91,96, 236,360,235,22,26,23,19,16,20,102,246,44,26,32,20,29,17,433,559,279,171,931,491,303,4517,2421,13101,8189,2345,1145,1209,1145,1081,1081,641,673,673,609, 577,609,373,199,107,419,247,57,41,27,29,36];;

Then,
for i in [1..123] do for j in [(i+1)..123] do if indexes[i]=indexes[j] then Print([i,j,Size(LowIndexSubgroupsFpGroup(G[i],8)),Size(LowIndexSubgroupsFpGroup(G[j],8))], " "); fi; od; od;

Obtaining:
[ 12, 31, 532, 284 ],[ 26, 34, 676, 702 ],[ 29, 44, 101, 84 ],[ 35, 36, 486, 396 ], [ 37, 58, 570, 1054 ], [ 37, 64, 570, 1054 ], [ 55, 61, 3346, 3346 ], [ 57, 63, 1658, 1658 ], [ 58, 64, 1054, 1054 ], [ 78, 86, 42, 47 ], [ 82, 88, 22, 24 ], [ 89, 122, 43, 54 ],[ 103, 105, 5180, 6428 ], [ 106, 107, 4380, 4380 ], [ 109, 110, 3076, 4324 ],[ 111, 113, 2532, 2532 ]

We still have to distinguish between:
G[55] and G[61], G[57] and G[63], G[58] and G[64], G[106] and G[107], G[111] and G[113].

Size(LowIndexSubgroupsFpGroup(G[55],9))-Size(LowIndexSubgroupsFpGroup(G[61],9)) 
is different from zero

Size(LowIndexSubgroupsFpGroup(G[57],9))-Size(LowIndexSubgroupsFpGroup(G[63],9)) 
is different from zero

Size(LowIndexSubgroupsFpGroup(G[58],9))-Size(LowIndexSubgroupsFpGroup(G[64],9)) 
is different from zero

Size(LowIndexSubgroupsFpGroup(G[106],16)) returns 55907
Size(LowIndexSubgroupsFpGroup(G[107],16)) returns 56419
so they're different (16 is the first natural number which satisfies that).

Size(LowIndexSubgroupsFpGroup(G[111],16)) returns 40787
Size(LowIndexSubgroupsFpGroup(G[113],16)) returns 41043
so they're different (16 is the first natural number which satisfies that).

In conclusion, the 123 lattices are non-isomorphic



