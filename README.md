# utl-extrema--of-mathematical-functions
Extrema of mathematical functions
    Extrema of mathematical functions                                                                                
                                                                                                                     
    Problem: Identify the extrema  of                                                                                
                                                                                                                     
        f(x) = sin(2x)*sin(x) over (-pi/2,pi/2) 
        
    github
    https://github.com/rogerjdeangelis/utl-extrema--of-mathematical-functions
                                                                                                                     
    Keep in mind that closed form solutions are quite rare in the domain od advanced mathematical analysys,          
    but when they exist either exactly or approximately they can lead to dramatic new knowledge.                     
                                                                                                                     
    SAS Forum                                                                                                        
    https://tinyurl.com/wbymtcb                                                                                      
    https://communities.sas.com/t5/Graphics-Programming/SAS-and-the-extrems-of-Mathematical-Function/m-p/603053      
                                                                                                                     
    *_                   _                                                                                           
    (_)_ __  _ __  _   _| |_                                                                                         
    | | '_ \| '_ \| | | | __|                                                                                        
    | | | | | |_) | |_| | |_                                                                                         
    |_|_| |_| .__/ \__,_|\__|                                                                                        
            |_|                                                                                                      
    ;                                                                                                                
                                                                                                                     
    data have;                                                                                                       
      pi=constant("PI");                                                                                             
      do x=-pi/2 to pi/2 by .05;                                                                                     
         fx12345678901234567890123456 = sin(2*x)*sin(x) ;                                                            
         output;                                                                                                     
      end;                                                                                                           
      drop pi;                                                                                                       
    run;quit;                                                                                                        
                                                                                                                     
    WORK.HAVE total obs=63                                                                                           
                                                                                                                     
    Obs        X        F_X                                                                                          
                                                                                                                     
      1    -1.57080   0.00000                                                                                        
      2    -1.52080   0.09971                                                                                        
      3    -1.47080   0.19768                                                                                        
      4    -1.42080   0.29220                                                                                        
      5    -1.37080   0.38166                                                                                        
     ...                                                                                                             
                                                                                                                     
    options ls=64 ps=44;                                                                                             
    proc plot data=have;                                                                                             
      plot fx12345678901234567890123456*x='*';                                                                       
    run;quit;                                                                                                        
                                                                                                                     
                             x                                                                                       
          -1.571     -0.471      0.629    1.729                                                                      
       1.0 -+----------+----------+----------+ 1.0                                                                   
           |                                 |                                                                       
           |f(x)=sin(2x)*sin(x) (-pi/2,pi/2) |                                                                       
       0.8 +                                 + 0.8                                                                   
           |      **                 **      |                                                                       
           |     *  *               *  *     |                                                                       
           |     *  *               *  *     |                                                                       
           |    *    *             *    *    |                                                                       
           |                                 |                                                                       
       0.6 +    *    *             *    *    + 0.6                                                                   
           |          *           *          |                                                                       
           |   *                         *   |                                                                       
           |          *           *          |                                                                       
           |   *                         *   |                                                                       
           |           *         *           |                                                                       
       0.4 +                                 + 0.4                                                                   
           |  *        *         *        *  |                                                                       
           |                                 |                                                                       
           |  *         *       *            |                                                                       
           |                    *         *  |                                                                       
           |            *                    |                                                                       
       0.2 + *           *     *             + 0.2                                                                   
           |                               * |                                                                       
           |             *     *             |                                                                       
           | *            *   *              |                                                                       
           |              *   *            * |                                                                       
           |               * *               |                                                                       
       0.0 +*              ***               + 0.0                                                                   
           |                                 |                                                                       
           -+----------+----------+----------+                                                                       
         -1.571     -0.471      0.629    1.729                                                                       
                            X                                                                                        
                                                                                                                     
    DX1   =  2*sin(x)*cos(2*x) + sin(2*x)*cos(x)                                                                     
    DX2   =  -5*sin(x)*sin(2*x) + 4*cos(x)*cos(2*x)                                                                  
    LOC   =  {0, -2*atan(sqrt(-sqrt(3) + 2)), 2*atan(sqrt(-sqrt(3) + 2))}                                            
                                                                                                                     
    *            _               _                                                                                   
      ___  _   _| |_ _ __  _   _| |_                                                                                 
     / _ \| | | | __| '_ \| | | | __|                                                                                
    | (_) | |_| | |_| |_) | |_| | |_                                                                                 
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                
                    |_|                                                                                              
    ;                                                                                                                
                                                                                                                     
    WORK.WANT total obs=3                                                                                            
                                                                                                                     
                            Sign     if neg then max                                                                 
      EXTREMA      f''(X)  MINMAX    if pos then min                                                                 
                                                                                                                     
       0.00000       1     Minimum                                                                                   
                                                                                                                     
      -0.95532      -1     Maximum                                                                                   
       0.95532      -1     Maximum                                                                                   
                                                                                                                     
                                                                                                                     
    WORK.MTAXPO total obs=6                                                                                          
                                                                                                                     
    FUNCTIONALS          CLOSED_FORMS                                                                                
                                                                                                                     
       DX1         2*sin(x)*cos(2*x) + sin(2*x)*cos(x)                                                               
       DX2         -5*sin(x)*sin(2*x) + 4*cos(x)*cos(2*x)                                                            
                                                                                                                     
       LOC         0, -2*atan(sqrt(-sqrt(3) + 2)), 2*atan(sqrt(-sqrt(3) + 2))                                        
                                                                                                                     
       LOC1        0                                                                                                 
       LOC2        -2*atan(sqrt(-sqrt(3) + 2))                                                                       
       LOC3        2*atan(sqrt(-sqrt(3) + 2))                                                                        
                                                                                                                     
                                                                                                                     
    First and secon derivatives                                                                                      
                                                                                                                     
    f`(x)   =  2*sin(x)*cos(2*x) + sin(2*x)*cos(x)                                                                   
    f``(x)  =  -5*sin(x)*sin(2*x) + 4*cos(x)*cos(2*x)                                                                
                                                                                                                     
    Extrema {0, -2*atan(sqrt(-sqrt(3) + 2)), 2*atan(sqrt(-sqrt(3) + 2))}                                             
                                                                                                                     
                                                                                                                     
    Second derivatives provide the type of maxima                                                                    
                                                                                                                     
    Minimum (f``(0)                             is negative                                                          
                                                                                                                     
    Maxima1  f``(-2*atan(sqrt(-sqrt(3) + 2)))   is positive                                                          
    Maxima2  f``(2*atan(sqrt(-sqrt(3) + 2)))    is positive                                                          
                                                                                                                     
                                                                                                                     
                             x                                                                                       
          -1.571     -0.471      0.629    1.729                                                                      
       1.0 -+----------+----------+----------+ 1.0                                                                   
           | f(x)=sin(2x)*sin(x) (-pi/2,pi/2)|                                                                       
           |                                 |                                                                       
       0.8 +                                 + 0.8                                                                   
           |      **                 **      |                                                                       
           |     * |*               * |*     |                                                                       
           |     * |*               * |*     |                                                                       
           |    *  | *             *  | *    |                                                                       
           |       |                  |      |                                                                       
       0.6 +    *  + *             *  + *    + 0.6                                                                   
           |       |  *           *   |      |                                                                       
           |   *   |                  |  *   |                                                                       
           |       |  *           *   |      |                                                                       
           |   *   |                  |  *   |                                                                       
           |       |   *         *    |      |                                                                       
       0.4 +       +                  +      + 0.4                                                                   
           |  *    |   *         *    |   *  |                                                                       
           |       |                  |      |                                                                       
           |  *    |    *       *     |      |                                                                       
           |       |            *     |   *  |                                                                       
           |       |    *             |      |                                                                       
       0.2 + *     +     *     *      +      + 0.2                                                                   
           |       |                  |    * |                                                                       
           |       |     *     *      |      |                                                                       
           | *     |      * 0 *       |      |                                                                       
           |       |      * ^ *       |    * |                                                                       
           |       |       *|*        |      |                                                                       
       0.0 +*      +       ***        +      + 0.0                                                                   
           |       |        |         |      |                                                                       
           -+------+----+----------+--+--------+                                                                     
         -1.571    |-0.471  0   0.629 |  1.729                                                                       
                   V        X         V                                                                              
                 -0.96   Minima     +0.96                                                                            
               Maxima              Maxima                                                                            
                                                                                                                     
    *                                                                                                                
     _ __  _ __ ___   ___ ___  ___ ___                                                                               
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|                                                                              
    | |_) | | | (_) | (_|  __/\__ \__ \                                                                              
    | .__/|_|  \___/ \___\___||___/___/                                                                              
    |_|                                                                                                              
    ;                                                                                                                
                                                                                                                     
    %utl_submit_py64('                                                                                               
    from sympy import *;                                                                                             
    import pyperclip;                                                                                                
    x = Symbol("x", domain=S.Reals);                                                                                 
    solve_domain = And(-pi/2 <= x, x < pi/2).as_set();                                                               
    dx1=diff(sin(2*x)*sin(x));                                                                                       
    print(dx1);                                                                                                      
    res=solveset(dx1, x, solve_domain);                                                                              
    print(res);                                                                                                      
    dx2=diff(dx1);                                                                                                   
    print(dx2);                                                                                                      
    tx1=str(dx1);                                                                                                    
    tx2=str(dx2);                                                                                                    
    tx3=str(res);                                                                                                    
    tx123=tx1+"@"+tx2+"@"+tx3;                                                                                       
    pyperclip.copy(tx123);                                                                                           
    ',return=frompy);                                                                                                
                                                                                                                     
    LOG                                                                                                              
                                                                                                                     
    2*sin(x)*cos(2*x) + sin(2*x)*cos(x)                                                                              
    {0, -2*atan(sqrt(-sqrt(3) + 2)), 2*atan(sqrt(-sqrt(3) + 2))}                                                     
    -5*sin(x)*sin(2*x) + 4*cos(x)*cos(2*x)                                                                           
                                                                                                                     
    %put &=frompy; /*  "@" delimiter  */                                                                             
                                                                                                                     
    FROMPY=2*sin(x)*cos(2*x) + sin(2*x)*cos(x)@                                                                      
           -5*sin(x)*sin(2*x) + 4*cos(x)*cos(2*x)@                                                                   
           {0, -2*atan(sqrt(-sqrt(3) + 2)),2*atan(sqrt(-sqrt(3) + 2))}                                               
                                                                                                                     
    data want;                                                                                                       
     if _n_=0 then do; %let rc=%sysfunc(dosubl('                                                                     
       /* get meta functionals */                                                                                    
       data meta;                                                                                                    
                                                                                                                     
         retain tx123 "&frompy";                                                                                     
                                                                                                                     
         dx1=scan(tx123,1,'@');                                                                                      
         dx2=scan(tx123,2,'@');                                                                                      
                                                                                                                     
         loc=compress(scan(tx123,3,'@'),"{}");                                                                       
                                                                                                                     
         loc1=scan(loc,1,",");                                                                                       
         loc2=scan(loc,2,",");                                                                                       
         loc3=scan(loc,3,",");                                                                                       
                                                                                                                     
         drop tx123;                                                                                                 
                                                                                                                     
         call symputx("dx1",dx1);                                                                                    
         call symputx("dx2",dx2);                                                                                    
         call symputx("loc1",loc1);                                                                                  
         call symputx("loc2",loc2);                                                                                  
         call symputx("loc3",loc3);                                                                                  
                                                                                                                     
       run;quit;                                                                                                     
       proc transpose data=meta out=mtaXpo(rename=(_name_=Functionals col1=Closed_Form));                            
       var _character_;                                                                                              
       run;quit;                                                                                                     
       '));                                                                                                          
     end;                                                                                                            
                                                                                                                     
     extrema  = &loc1; link evl;                                                                                     
     extrema  = &loc2; link evl;                                                                                     
     extrema  = &loc3; link evl;                                                                                     
     stop;                                                                                                           
                                                                                                                     
     evl:                                                                                                            
       x=extrema ;                                                                                                   
       sign=sign(&dx2);                                                                                              
       if sign<0 then MinMax="Maximum";else MinMax="Minimum";output;                                                 
       return;                                                                                                       
    run;quit;                                                                                                        
