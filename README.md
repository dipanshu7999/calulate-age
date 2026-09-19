def age_calculate():
    import datetime as dt
    today = dt.date.today()
    birthday = list(map(int,input("enter date of birth(dd-mm-yyyy):").split('-')))
    cd,cm,cy = today.day,today.month,today.year
    bd,bm,by = birthday[0],birthday[1],birthday[2]
    data = {1:31,2:28,3:31,4:30,5:31,6:30,7:31,8:31,9:30,10:31,11:30,12:31}
    days,month,year = 0,0,0
    if cd >= bd:
        days = cd - bd
    else:
        if cm != 1:
            cm = cm - 1
            if cm == 2:
                if (cy % 4 == 0 and cy % 100 != 0) or (cy % 400 == 0):
                    data[2] = 29
                else:
                    data[2] = 28        
            days = (cd + data[cm]) - bd
        else:
            cm = 12
            cy = cy - 1
            days = (cd + 31) - bd

    if cm >= bm:
        month = cm - bm
    else:
        cy = cy - 1
        month = (cm + 12) - bm
    year = cy - by
    return f"You lived {year} Years {month} Month and {days} Days"

print(age_calculate()) # calulate-age
you can check your age here
