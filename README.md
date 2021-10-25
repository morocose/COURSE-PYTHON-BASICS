# COURSE-PYTHON-BASICS
#My geometric calculator 
class Rectangle(object):
 "Class of rectangles"
 def __init__(self,length,breadth):
     "The constructor of the class rectangles"
     self.L, self.l = length,breadth
 def area(self):
     "calculation of the area"
     self.rec_area = self.L*self.l
     return self.rec_area
class Square(Rectangle):
    "Class of squares"
    def __init__(self,side):
        "the constractor for the Class squares"
        Rectangle.__init__(self,side,side)# we call the constructor of the class of rectangles
        
        self.c = side
class Cube(Square):
    "Class of cubes"
    def __init__(self,side):
        "the constractor for the Classe squares"
        Square.__init__(self,side)# we call the constructor of the class of squares
        self.c = side
    def area(self):
        "calculation of the area"
        self.cube_area = (self.c)**2*6
        return self.cube_area
    def volume(self):
        "calculation of the volume"
        self.cube_vol = (self.c)**3
        return self.cube_vol
class Parallelepiped(Rectangle):
    "Class of Parallelepipeds with a rectangular base"
    def __init__(self,length,breadth,height):
        "the constractor for the Classe Parallelepipeds with a rectangular base"
        Rectangle.__init__(self,length,breadth)# we call the constructor of the class of rectangles
        self.h = height
    def area(self):
        "calculation of the area"
        self.para_area = 2*self.h*self.L+2*self.h*self.l+2*self.L*self.l
        return self.para_area
    def volume(self):
        "calculation of the volume"
        self.para_vol = self.h*self.L*self.h
        return self.para_vol
class Parallelepiped_S(Square):
    "Class of Parallelepipeds with a square base"
    def __init__(self,side,height):
        "the constractor for the Classe Parallelepipeds with a square base"
        Square.__init__(self,side)# we call the constructor of the class of squares
        self.h = height
    def area_2(self):
        "calculation of the area"
        self.para_area = 4*self.c*self.h + 2*(self.c)**2
        return self.para_area
    def volume_2(self):
        "calculation of the volume"
        self.para_vol = self.h*(self.c)**2
        return self.para_vol
class Circle(object):
    "Class of circles"
    def __init__(self,ray):
        "the constractor for the Class of circles"
        self.r = ray
    def area(self):
        "calculation of the area"
        self.cer_area = 3.14*(self.r)**2
        return self.cer_area
class Sphere(Circle):
    "Class of spheres"
    def __init__(self):
        "the constractor for the Class of spheres"
        Circle.__init__(self,ray)
    def area(self):
        "calculation of the area"
        self.sph_area = 4*3.14*(self.r)**2
        return self.sph_area
    def volume(self):
        "calculation of the volume"
        self.sph_vol = 4/3*3.14*(self.r)**3
        return self.sph_vol
class Cylinder(Circle):
    "Class of circles"
    def __init__(self,ray,height):
        "the constractor for the Class of cylinders"
        Circle.__init__(self,ray)# we call the constructor of the class of circles
        self.H = height
    def area(self):
        "calculation of the area"
        self.cyl_area = 2*3.14*(self.r)**2 + 2*3.14*(self.r)*self.H
        return self.cyl_area
    def volume(self):
        "calculation of the volume"
        self.cyl_vol = 3.14*((self.r)**2)*self.H
        return self.cyl_vol
class Cone(Circle):
    "Class of circles"
    def __init__(self,ray,apothem):
        "the constractor for the Class of cones"
        Circle.__init__(self,ray)# we call the constructor of the class of circles
        self.S = apothem
    def area(self):
        "calculation of the area"
        self.cone_area = 1/3*3.14*((self.r)**2)*self.S
        return self.cone_area
    def volume(self):
        "calculation of the volume"
        self.cone_vol = 3.14*(self.r)*self.S + 3.14*(self.r)**2
        return self.cone_vol
class Triangle(object):
    "Class of triangles"
    def __init__(self,side,height):
        "the constractor for the Class of triangles"
        self.c = side
        self.h = height
    def area(self):
        "returning the value of the area"
        return self.triangle_area(side,height)

    @staticmethod
    def triangle_area(c,h):
        "calculation of the area"
        return c*h/2
class Trapezoid(object):
    "Class of trapezoids"
    def __init__(self,small_base,big_base,height):
        "the constractor for the Class of trapezoids"
        self.b = small_base
        self.h = height
        self.B = big_base
    def area(self):
        "returning the value of the area"
        return self.trapezoid_area(small_base,big_base,height)

    @staticmethod
    def trapezoid_area(b,B,h):
        "calculation of the area"
        return (b+B)*h/2
class Pyramid(Square):
    "Class of pyramids with a square base"
    def __init__(self,side,apothem):
        "the constructor of the class of pyramids with a square base"
        Square.__init__(self,side)# we call the constructor of the class of squares
        self.S = apothem
    def area(self):
        "returning the value of the area"
        return self.pyramid_area(side,apothem)
    @staticmethod
    def pyramid_area(c,S):
        "calculation of the area"
        return 4*c*S/2+c**2
    def volume(self):
        "returning the value of the volume"
        return self.pyramid_vol(side,apothem)

    @staticmethod
    def pyramid_vol(c,S):
        "calculation of the volume"
        return 1/3*(c**2)*S
class Pyramid_R(Rectangle):
    "Class of pyramids with a rectangular  base"
    def __init__(self,length,breadth,apothem):
        "the constructor of the class of pyramids with a rectangular base"
        Rectangle.__init__(self,length,breadth)# we call the constructor of the class of rectangles
        self.S = apothem
    def area_R(self):
        "returning the value of the area"
        return self.pyramid_area(length,breadth,apothem)

    @staticmethod
    def pyramid_area(L,l,S):
        "calculation of the area"
        return ((l+L)*2*S)/2 + l*L
    def volume_R(self):
        "returning the value of the volume"
        return self.pyramid_vol(length,breadth,apothem)

    @staticmethod
    def pyramid_vol(L,l,S):
        "calculation of the volume"
        return 1/3*(l*L)*S
class Pyramid_T(object):
    "Class of pyramids with a triangualar  base"
    def __init__(self,side1,side2,side3,height1,height2,height3,apothem):
        "the constructor of the class of pyramids with a triangular base"
        self.S = apothem
        self.c1 = side1
        self.c2 = side3
        self.c3 = side3
        self.h1 = height1
        self.h2 = height2
        self.h3 = height3
    def area_T(self):
        "calculation of the area"
        self.pyramid_T_area = (self.c1+self.c2+self.c3)*self.S + self.c1*self.h1/2
        return self.pyramid_T_area
    def volume_T(self):
        "calculation of the volume"
        self.pyramid_T_vol = 1/3*self.c1*self.h1/2*self.S
        return self.pyramid_T_vol
class Losange(object):
    "Class of losanges"
    def __init__(self,big_diagonal,small_diagonal):
        "the constructor of the class of losanges"
        self.D = big_diagonal
        self.d = small_diagonal
    def area(self):
        "calculation of the area"
        return self.losange_area(big_diagonal,small_diagonal)

    @staticmethod
    def losange_area(D,d):
        "calculation of the area"
        return D*d/2
if __name__ == "__main__":
    while True:
        choix1 = str(input("would you like to calculate {volume} or {area} of shapes either enter {S} to stop : "))
        selection = choix1.lower()
        if selection == "volume" or selection == "area":
            choix2 = str(input("Please type your shape's name: "))
            choice = choix2.lower()
            if choice == "rectangle":
                if selection== "area":
                    length= float(input("Please tell me the value of the length: "))
                    breadth = float(input("Please tell me the value of the breadth: "))
                    r1 = Rectangle(length,breadth)
                    print(f"Your {choice}'s area is {r1.area()}")
                else:
                    print(f"{choice} doesn't have a volume")
            elif choice == "square":
                if selection== "area":
                    side = float(input("Please tell me the value of the square side: "))
                    r2 = Square(side)
                    print(f"Your {choice}'s area is {r2.area()}")
                else:
                    print(f"{choice} doesn't have a volume")
            elif choice == 'cube':
                side = float(input("Please tell me the value of the cube side: "))
                r3 = Cube(side)
                if selection== "area":
                    print(f"Your {choice}'s area is {r3.area()}")
                elif selection == "volume":
                    print(f"Your {choice}'s volume is {r3.volume()}")
            elif choice == "parallelepiped":
                choix3 = str(input(f"please tell me the base of your {choice}: "))
                decision = choix3.lower()
                if decision=='rectangle':
                    length= float(input("Please tell me the value of the length: "))
                    breadth = float(input("Please tell me the value of the breadth: "))
                    height = float(input("Please tell me the value of the height: "))
                    r4 = Parallelepiped(length,breadth,height)
                    if selection=="area":
                        print(f"Your {choice}'s area is {r4.area()}")
                    elif selection=="volume":
                        print(f"Your {choice}'s volume is {r4.volume()}")
                elif decision=='square':
                    side = float(input("Please tell me the value of the side: "))
                    height = float(input("Please tell me the value of the height: "))
                    r4 = Parallelepiped_S(side,height)
                    if selection=="area":
                        print(f"Your {choice}'s area is {r4.area_2()}")
                    elif selection=="volume":
                        print(f"Your {choice}'s volume is {r4.volume_2()}")
                    else:
                        print("please enter correctly the input")
            elif choice == "circle":
                if selection== "area":
                    ray = float(input("Please tell me the value of the circle ray: "))
                    r5 = Circle(ray)
                    print(f"Your {choice}'s area is {r5.area()}")
                else:
                    print(f"{choice} doesn't have a volume")
            elif choice == "sphere":
                ray = float(input("Please tell me the value of the sphere ray: "))
                r6 = Sphere()
                if selection=="area":
                    print(f"Your {choice}'s area is {r6.area()}")
                elif selection=="volume":
                    print(f"Your {choice}'s volume is {r6.volume()}")
            elif choice == "cylinder":
                ray = float(input("Please tell me the value of the cylinder ray: "))
                height = float(input("Please tell me the value of the cylinder height: "))
                r7 = Cylinder(ray,height)
                if selection=="area":
                    print(f"Your {choice}'s area is {r7.area()}")
                elif selection=="volume":
                    print(f"Your {choice}'s volume is {r7.volume()}")
            elif choice == "cone":
                ray = float(input("Please tell me the value of the cone ray: "))
                apothem = float(input("Please tell me the value of the cone apothem: "))
                r8 = Cone(ray,apothem)
                if selection=="area":
                    print(f"Your {choice}'s area is {r8.area()}")
                elif selection=="volume":
                    print(f"Your {choice}'s volume is {r8.volume()}")
            elif choice == "triangle":
                if selection== "area":
                    side = float(input("Please tell me the value of a side of the triangle: "))
                    height = float(input("Please tell me the value of the height relative to that side: "))
                    r9 = Triangle(side,height)
                    print(f"Your {choice}'s area is {r9.area()}")
                else:
                    print(f"{choice} doesn't have a volume")
            elif choice == "trapezoid":
                if selection== "area":
                    small_base = float(input("Please tell me the value of the trapezoid small_base: "))
                    big_base = float(input("Please tell me the value of the trapezoid big_base: "))
                    height = float(input("Please tell me the value of the trapezoid height: "))
                    r10 = Trapezoid(small_base,big_base,height)
                    print(f"Your {choice}'s area is {r10.area()}")
                else:
                    print(f"{choice} doesn't have a volume")
            elif choice == "pyramid":
                choix4 = str(input(f"please tell me the base of your {choice}: "))
                decision2 = choix4.lower()
                if decision2=='square':
                    side = float(input("Please tell me the value of the pyramid side: "))
                    apothem = float(input("Please tell me the value of the pyramid apothem: "))
                    r11 = Pyramid(side,apothem)
                    if selection=="area":
                        print(f"Your {choice}'s area is {r11.area()}")
                    elif selection=="volume":
                        print(f"Your {choice}'s volume is {r11.volume()}")
                elif decision2 =='rectangle':
                    length= float(input("Please tell me the value of the length: "))
                    breadth = float(input("Please tell me the value of the breadth: "))
                    apothem = float(input("Please tell me the value of the apothem: "))
                    r11 = Pyramid_R(length,breadth,apothem)
                    if selection=="area":
                        print(f"Your {choice}'s area is {r11.area_R()}")
                    elif selection=="volume":
                        print(f"Your {choice}'s volume is {r11.volume_R()}")
                elif decision2=="triangle":
                    side1= float(input("Please tell me the value of the first side: "))
                    height1 = float(input("Please tell me the value of the height relative to the side1: "))
                    side2 = float(input("Please tell me the value of the second side: "))
                    height2= float(input("Please tell me the value of the height relative to the side2 : "))
                    side3 = float(input("Please tell me the value of the third side: "))
                    height3 = float(input("Please tell me the value of the height relative to the side3: "))
                    apothem = float(input("Please tell me the value of the apothem: "))
                    r11 = Pyramid_T(side1,side2,side3,height1,height2,height3,apothem)
                    if selection=="area":
                        print(f"Your {choice}'s area is {r11.area_T()}")
                    elif selection=="volume":
                        print(f"Your {choice}'s volume is {r11.volume_T()}")
                else:
                    print("please enter correctly the input")
            elif choice == "losange":
                if selection== "area":
                    big_diagonal= float(input("Please tell me the value of the losange big_diagonal: "))
                    small_diagonal = float(input("Please tell me the value of the losange small_diagonal: "))
                    r12 = Losange(big_diagonal,small_diagonal)
                    print(f"Your {choice}'s area is {r12.area()}")
                else:
                    print(f"{choice} doesn't have a volume")
            else:
                print("Please Enter correct input!")
        if selection == 's' or selection=='S':
            break
        else:
            print("Please Enter correctly {volume} or {area}!")

