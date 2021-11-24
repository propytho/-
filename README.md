import tkinter as tk

def show_output():
    number = int(number_input.get())

    if number == 0:
        output_label.configure(text='ก็รู้อยู่แล้วนิ0คูณตัวอะไรก็ตามก็ได้0เหมือนคแนนของคุณ', height=5)
        return

    output = ''
    for i in range(1, 51):
        output += str(number) + ' X ' + str(i)
        output += ' = ' + str(number * i) + '\n'

    output_label.configure(text=output)

window = tk.Tk()
window.title('WOWZA')
window.minsize(width=400, height=400)

title_label = tk.Label(master=window, text='สูตรคูณแม่(ได้ถึงแม่999999999999999999999999999999999999999999999)')
title_label.pack(pady=20)

number_input = tk.Entry(master=window)
number_input.pack()

go_button = tk.Button(
    master=window, text='ได้แก่', command=show_output, width=15, height=2
)
go_button.pack(pady=20)

output_label = tk.Label(master=window)
output_label.pack()

window.mainloop()
