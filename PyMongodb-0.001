__author__ = 'Yarmiky Shilla'
#Using Mongodb and Python
# 1. Create connection to Pymongo
# 2. Create document
# 3. Insert document
# 4. Delete document
# 5. Update document
# 6. Display document

def get_db():
    from pymongo import MongoClient
    client = MongoClient('localhost:27017')
    db = client.myFirstMB3.studentrecord
    return db


def create_document():
    student_record = {}
    return student_record


def add_student(db):
    flag = True
    while(flag):
     student_name,student_grade = input("Enter student name and grade: ").split(',')
     student_record = {'name': student_name, 'grade': student_grade}
     db.insert(student_record)
     flag = input('Enter another record? ')
     if(flag[0].upper() == 'N'):
      flag = False

def delete_student(db):
    flag = True
    while(flag):
     student_name =input("Enter student Name to delete:")
     student_record1 = {'name':student_name}
     db.remove(student_record1)
     flag = input('Delete another Record?')
     if(flag[0].upper() == 'N'):
        flag = False

def update_student(db):
    flag = True
    while(flag):
        student_name,student_grade =input("Enter student Name and grade to Update:").split(',')
        student_name1,student_grade1 =input("Enter New student Name and grade to change to:").split(',')
        student_record2= {'name': student_name,'grade': student_grade}
        student_record3= {'name': student_name1,'grade': student_grade1}
        db.update(student_record2,student_record3)
        flag = input('Update another Record?')
        if(flag[0].upper() == 'N'):
            flag = False

def get_student(db):
    result1 = db.find()
    return result1


if __name__ == "__main__":
    x = True
    while(x):
        db = get_db()
        answer =input("Enter: 1. Inserting, 2 as Deleting, 3 as Updating and 4 as Display::->")
        if(answer == '1'):
            add_student(db)
        elif(answer == '2'):
            delete_student(db)
        elif(answer == '3'):
            update_student(db)
        else:
            pat = get_student(db)
            print()
            print('+-+-+-+-+-+-+-+-+-+-+-+-+-+-')
            print('Name+-+-+-+-Grade+-+-+-+-+-+-')
            for record in pat:print(record['name'] + ',', record['grade'])
        x =input('Do you want to continue?')
        if(x[0].upper() =='N'):
            x =False
