# Ένα σχολείο αποτελείται από καθηγηές, μαθητές, αίθουσες, μαθήματα, ωράριο, εξαιτάσεις και διευθυντή
class School:  # 1) Δημιουργία κλάσης σχολείο και κατασκευαστή
    def __init__(self, name, teachers, students, school_classes, lessons, hours_teaching, exams, director):
        self.name = name
        self.teachers = teachers
        self.students = students
        self.school_classes = school_classes
        self.lessons = lessons
        self.hours_teaching = hours_teaching
        self.exams = exams
        self.director = director
# 2) Δημιουργία setters και getters

    def set_name(self, name):
        self.name = name

    def get_name(self):
        return self.name

    def set_teachers(self, teachers):
        self.teachers = teachers

    def get_teachers(self):
        return self.teachers

    def set_students(self, students):
        self.students = students

    def get_students(self):
        return self.students

    def set_school_classes(self, school_classes):
        self.school_classes = school_classes

    def get_school_classes(self):
        return self.school_classes

    def set_lessons(self, lessons):
        self.lessons = lessons

    def get_lessons(self):
        return self.lessons

    def set_hours_teaching(self, hours_teaching):
        self.hours_teaching = hours_teaching

    def get_hours_teaching(self):
        return self.hours_teaching

    def set_exams(self, exams):
        self.exams = exams

    def get_exams(self):
        return self.exams

    def set_director(self, director):
        self.director= director

    def get_director(self):
        return self.director


class Professors(School):  # 3) Δημιουργία κλάσης Καθηγητές η οποία θα κληρωνομεί στοιχεία της κλάσης σχολείο
    def __init__(self, name,teachers, students, school_classes, lessons, hours_teaching, exams, director, reading_time):
        super().__init__(name,teachers, students, school_classes, lessons, hours_teaching, exams, director)  # 4 Με τη super δηλώνουμε ποια στοιχεία κληρωνωμεί
        self.reading_time = reading_time  # 5) O καθηγητης εχει και επιπροσθετο στοχείο τον χρόνο διαβάσματος

    def set_reading_time(self, reading_time):  #  6) Δημιουργια setters  και getters
        self.reading_time = reading_time

    def get_reading_time(self):
        return self.reading_time


class Students(Professors):  # 4) Δημιουργία κλάσης Καθηγητές η οποία θα κληρωνομεί στοιχεία της κλάσης Καθηγητες
    def __init__(self, name, teachers, students, school_classes, lessons, hours_teaching, exams, director, reading_time, sport_time):
        super().__init__(name, teachers, students, school_classes, lessons, hours_teaching, exams, director, reading_time)
        self.sport_time = sport_time

    def set_sport_time(self, sport_time):
        self.sport_time = sport_time

    def get_sport_time(self):
        return  self.sport_time


class Director(School):
    def __init__(self, name, teachers, students, school_classes, lessons, hours_teaching, exams, director, program_design):
        super().__init__(name, teachers, students, school_classes, lessons, hours_teaching, exams, director)
        self.program_design = program_design

    def set_program_design(self, program_design):
        self.program_design = program_design

    def get_program_design(self):
        return self.program_design


def main():


    Piramatiko_Lykeio = School('Piramatiko_Lykeio', 20, 300, 30, 40, 100, 100, 1)
    Aggelos = Students('Piramatiko_Lykeio',10, None, 5, 10, 35, 15, 1, 40, 14)
    Stathis = Students('Piramatiko_Lykeio', 12, None, 6, 11, 39, 17, 1, 45, 12)
    Petros = Students('Piramatiko_Lykeio', 13, None, 7, 12, 42, 14, 1, 48, 10)
    Alex = Students('Piramatiko_Lykeio', 11, None, 9, 15, 44, 20, 1, 50, 12)
    Makis = Students('Piramatiko_Lykeio', 12, None, 10, 16, 42, 18, 1, 44, 10)
    Sakis = Students('Piramatiko_Lykeio', 13, None, 12, 15, 45, 19, 1, 42, 9)
    Takis = Students('Piramatiko_Lykeio', 15, None, 13, 16, 48, 20, 1, 55, 7)
    Mr_Karalis = Professors('Piramatiko_Lykeio', None, 120, 8, 5, 40, None, 1, 15)
    Mr_Georgiou = Professors('Piramatiko_Lykeio', None, 140, 10, 8, 50, None, 1, 18)
    Mr_Nikolaou = Professors('Piramatiko_Lykeio', None, 100, 6, 7, 32, None, 1, 10)
    Supervisor_Konstantinou = Director('Piramatiko_Lykeio', 20, 350, 2, 5, 10, None, None, "sxhool_Design manager")

    print('Welcome to', Piramatiko_Lykeio.set_name)


    if Aggelos.exams < 16:
        print("You loose in panhellenic exams \n"
              "Plese read more")

        Aggelos.set_reading_time(49)
        Aggelos.set_sport_time(12)
        Aggelos.set_exams(17)
    else:
        print("Good job, keep going")

    print("O Αγγελος βελτίωσε τους βαθμούς του sto", Aggelos.exams, "\n",
          "χρειάστηκε να διαβάζει πλέον ", Aggelos.reading_time, "hours", "\n",
          "και να μειώσει τις ώρες που αθλείται σε", Aggelos.sport_time)

    if Mr_Nikolaou.hours_teaching < 40:
        print("O κύριος Νικολάου λίγες ώρες \n",
              "Θα σου αυξήσουμε τις ωρες")

        Mr_Nikolaou.set_hours_teaching(40)
        Mr_Nikolaou.set_students(120)
        Mr_Nikolaou.set_school_classes(9)
        Mr_Nikolaou.set_lessons(12)
        Mr_Nikolaou.set_reading_time(40)

    print()
    print("O κύριος Νικολάου πλέον διδάσκει", Mr_Nikolaou.hours_teaching, "ωρες", "\n",
          "πλέον έχει ", Mr_Nikolaou.students, "μαθητές", "\n",
          "διδάσκει πλέον σε ", Mr_Nikolaou.school_classes, "αίθουσες", "\n",
          "είναι υπεύθυνος για", Mr_Nikolaou.lessons, "μαθήματα", "\n",
           "και πλέον διαβάζει", Mr_Nikolaou.reading_time, "ώρες")
    print()
    
    Average_exams = ((Aggelos.exams + Stathis.exams + Petros.exams + Alex.exams + Makis.exams + Sakis.exams + Takis.exams)  / 7)
    print(Average_exams)
    if Average_exams <= 18.5:
        print("Το σχολειο απετυχε ")
        print("O diefthintis einai o ipefthinos\n"
              "O diefthintis metatithetai")
        Supervisor_Konstantinou.set_director("Supervisor_Mixail")
        print("O neos diefthintis tou",  Piramatiko_Lykeio.name, "einai o",   Supervisor_Konstantinou.director)

    else:
        print('To σχολείο πέτυχε, οι μαθητές πέρασαν στις σχολές τους')


main()





