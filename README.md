# Matchmaker_2
f = open('After_modification_HPG.txt', 'r' )
data = f.readlines()
list_1=[]
list_2 = []
list_3 = []
list_4 = []
list_5 = []
list_6 = []

f.close()


for line in data:
    line = line.strip().split()
    list_1.append(float(line[0]))
    list_3.append(float(line[2]))
    list_2.append(line[1])
    list_4.append(line[3])
    
f1 = open('Peak_on.txt', 'r' )
data1 = f1.readlines()


f1.close()


for line in data1:
    line = line.strip().split()
    list_5.append(float(line[0]))
    list_6.append(line[1])
    
f_out = open('FGF_xxx_on_match.txt', 'w' )
for i in range(len(list_1)):
    for j in range(len(list_5)):
        a = float(list_3[i]-list_5[j])
        if -0.1 <= a and a <= 0.0 or 0.0 <= a and a <= 0.1:
            f_out.write("%f\t%s\t%f\t%s\t%f\t%s\t\n" % (list_1[i],list_2[i], list_3[i], list_4[i], list_5[j],list_6[j]) )
f_out.close()
