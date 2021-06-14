import tkinter as ti
from pygame.locals import *
import os
import random


main_menu = ti.Tk()
screen_width = round(main_menu.winfo_screenwidth()/2)
screen_height = round(main_menu.winfo_screenheight()/2)

main_menu.title(  'Gra w tkinter'  )

main_menu.geometry( str(screen_width) +'x'+ str(screen_height) +'+'+ str(round(screen_width/2)) +'+'+ str(round(screen_height/2 )) )

war = ti.IntVar()
war_mod = ti.Checkbutton(main_menu, text = " WAR mod ", variable = war , \
    onvalue = True , offvalue = False, height=5, width = 20)
war_mod.place( x = screen_width * 0.43 , y = screen_height * 0.2 )


    
boool = random.choice([[0],[1]])
blue_symbol=boool[0:2]

moves=[]


my_exit = ti.Button( main_menu , text = """
   To finish click here   
""" , background = "red" , command = exit )
my_exit.place(  x = round( screen_width * 0.45 ) , y = round( screen_height * 0.8 )  )

def go():
    """Start new game"""
    root = ti.Tk()
    Playfield=[]
    for i in range(3):
        Playfield_27=[]
        for j in range(3):
            Playfield_9=[]
            for k in range(3):
                Playfield_9.append([2,2,2])
            Playfield_27.append(Playfield_9)
        Playfield.append(Playfield_27)
    #if war.get()

    SCREEN_WIDTH = round(root.winfo_screenwidth()*3/5)
    SCREEN_HEIGHT = round(root.winfo_screenheight()*3/5)
    root.title(  'TIC TAC TOE 2'  )
    root.geometry( str(SCREEN_WIDTH) +'x'+ str(SCREEN_HEIGHT) +'+'+ str(round(SCREEN_WIDTH/3)) +'+'+ str(round(SCREEN_HEIGHT/3 )) )


    

    

    def Is_win(frame):
        if type(frame)!=list : return False
        if  ( frame[1][1] in (0,1) ) and (   frame[0][1]==frame[1][1]==frame[2][1] or frame[0][0]==frame[1][1]==frame[2][2] or frame[0][2]==frame[1][1]==frame[2][0] or frame[1][0]==frame[1][1]==frame[1][2]   ):
            return True
        if ( frame[0][0] in (0,1) ) and (   frame[0][1]==frame[0][0]==frame[0][2] or frame[0][0]==frame[1][0]==frame[2][0]   ) :
            return True
        if ( frame[2][2] in (0,1) ) and (   frame[2][1]==frame[2][0]==frame[2][2] or frame[0][2]==frame[1][2]==frame[2][2]   ) :
            return True
        else:
            return False
    def where_win(frame):
        if type(frame)!=list : return False
        if  ( frame[1][1] in (0,1) ) and (   frame[0][1]==frame[1][1]==frame[2][1] or frame[0][0]==frame[1][1]==frame[2][2] or frame[0][2]==frame[1][1]==frame[2][0] or frame[1][0]==frame[1][1]==frame[1][2]   ):
            return frame[1][1]
        if ( frame[0][0] in (0,1) ) and (   frame[0][1]==frame[0][0]==frame[0][2] or frame[0][0]==frame[1][0]==frame[2][0]   ) :
            return frame[0][0]
        if ( frame[2][2] in (0,1) ) and (   frame[2][1]==frame[2][0]==frame[2][2] or frame[0][2]==frame[1][2]==frame[2][2]   ) :
            return frame[2][2]
        else:
            return False
    life_bar_red= ti.Canvas(
    root,
    height=SCREEN_HEIGHT,
    width=round(SCREEN_WIDTH*0.04),
    bg="red")
    life_bar_red.place( x= round(SCREEN_WIDTH*0.96) , y = 0 )

    TTT_width= round(SCREEN_WIDTH*0.9)
    TTT_height= round(SCREEN_HEIGHT*0.9)

    canvas = ti.Canvas(
    root,
    height=TTT_height,
    width=TTT_width,
    bg="white")
    canvas.place( x= SCREEN_WIDTH*0.05 , y = 0 )
    canvas.create_rectangle( TTT_width , TTT_height , 0 , 0 , fill='orange')
    
    life_bar_blue= ti.Canvas(
    root,
    height=SCREEN_HEIGHT,
    width= round(SCREEN_WIDTH*0.04),
    bg="blue")
    life_bar_blue.place( x= 0 , y = 0 )

    def close():
        root.destroy()

    my_exit_in = ti.Button( root , text = """     Click here to exit     """ , background = "red" , command = close )
    my_exit_in.place(  x = round( SCREEN_WIDTH * 0.6 ) , y = round( SCREEN_HEIGHT * 0.95 )  )
    
    
    
    def draw_grid():
        canvas.create_line( round( TTT_width * 31/94 ) , TTT_height , round( TTT_width * 31/94 ) , 0 , fill = "black" , width=round( TTT_width * 1/47 ) )
        canvas.create_line( round( TTT_width * 63/94 ) , TTT_height , round( TTT_width * 63/94 ) , 0 , fill = "black" , width=round( TTT_width * 1/47 ) )
        canvas.create_line( TTT_width , round( TTT_height * 31/94 ) , 0 , round( TTT_height * 31/94 ) , fill = "black" , width=round( TTT_height * 1/47 ) )
        canvas.create_line( TTT_width , round( TTT_height * 63/94 ) , 0 , round( TTT_height * 63/94 ) , fill = "black" , width=round( TTT_height * 1/47 ) )
        for i in range(3):
            for j in range(3):
                if type(Playfield[i][j])!=list : continue
                left_up=( TTT_height*(2-i)*16/47 , TTT_width*j*16/47 )
                in_width = TTT_width*15/47
                in_height = TTT_height*15/47
                canvas.create_line( round( left_up[1] + in_width*21/60 ) , round( left_up[0] + in_height*1/15 ) , round( left_up[1] + in_width*21/60 ) , round( left_up[0] + in_height*14/15 ) , fill = "black" , width=round( in_width * 1/30 ) )
                canvas.create_line( round( left_up[1] + in_width*39/60 ) , round( left_up[0] + in_height*1/15 ) , round( left_up[1] + in_width*39/60 ) , round( left_up[0] + in_height*14/15 ) , fill = "black" , width=round( in_width * 1/30 ) )
                canvas.create_line( round( left_up[1] + in_width*1/15 ) , round( left_up[0] + in_height*21/60 ) , round( left_up[1] + in_width*14/15 ) , round( left_up[0] + in_height*21/60 ) , fill = "black" , width=round( in_height * 1/30 ) )
                canvas.create_line( round( left_up[1] + in_width*1/15 ) , round( left_up[0] + in_height*39/60 ) , round( left_up[1] + in_width*14/15 ) , round( left_up[0] + in_height*39/60 ) , fill = "black" , width=round( in_height * 1/30 ) )
    draw_grid()
    def draw_symbols():
        for i1 in range(3):
            for j1 in range(3):
                left_up=( TTT_height*(2-i1)*16/47 , TTT_width*(j1)*16/47 )
                in_width = TTT_width*15/47
                in_height = TTT_height*15/47
                if type(Playfield[i1][j1])==list :
                    for i2 in range(3):
                        for j2 in range(3):
                            left_up_blocks = ( left_up[0]+in_height*(2+(2-i2)*9)/30 , left_up[1]+in_width*(2+(j2)*9)/30 )
                            width_block = in_width*4/15
                            height_block = in_height*4/15
                            if Playfield[i1][j1][i2][j2]==1 :
                                line_width_in_block = max( round(width_block) , round(height_block) )/10
                                canvas.create_line( round( left_up_blocks[1] + width_block*2/15 ) , round( left_up_blocks[0] + height_block*2/15 ) , round( left_up_blocks[1] + width_block*13/15 ) , round( left_up_blocks[0] + height_block*13/15 ) , fill = "black" , width=line_width_in_block )
                                canvas.create_line( round( left_up_blocks[1] + width_block*2/15 ) , round( left_up_blocks[0] + height_block*13/15 ) , round( left_up_blocks[1] + width_block*13/15 ) , round( left_up_blocks[0] + height_block*2/15 ) , fill = "black" , width=line_width_in_block )
                            if Playfield[i1][j1][i2][j2]==0:
                                R_in=min( round(width_block) , round(height_block) )*4/9
                                canvas.create_oval( round( left_up_blocks[1] + width_block/2 - R_in ) , round( left_up_blocks[0] + height_block/2 - R_in ) , round( left_up_blocks[1] + width_block/2 + R_in ) , round( left_up_blocks[0] + height_block/2 + R_in ) )
                else :
                    line_width = max( round(in_width) , round(in_height) )/15
                    if Playfield[i1][j1]==1:
                        canvas.create_line( round( left_up[1] + in_width*2/15 ) , round( left_up[0] + in_height*2/15 ) , round( left_up[1] + in_width*13/15 ) , round( left_up[0] + in_height*13/15 ) , fill = "black" , width=line_width )
                        canvas.create_line( round( left_up[1] + in_width*2/15 ) , round( left_up[0] + in_height*13/15 ) , round( left_up[1] + in_width*13/15 ) , round( left_up[0] + in_height*2/15 ) , fill = "black" , width=line_width )
                    else:
                        R=min( round(in_width) , round(in_height) )*2/5
                        canvas.create_oval( round( left_up[1] + in_width/2 - R ) , round( left_up[0] + in_height/2 - R ) , round( left_up[1] + in_width/2 + R ) , round( left_up[0] + in_height/2 + R ) )

    draw_symbols()
    
    def is_full(frame):
        if type(frame)!=list:
            return False
        for i in frame:
            for val in i:
                if val==2:
                    return False
        else:return True

    def restart(frame):
        if type(frame)!=list:
            return False
        for i in range(3):
            for val in range(3):
                frame[i][val]=2
                
    blue_live=[10]
    red_live=[10]


    def clear():
        for i in range(3):
            for j in range(3): 
                Playfield[i][j]=[[2,2,2],[2,2,2],[2,2,2]]
        canvas.delete('all')
        canvas.create_rectangle( TTT_width , TTT_height , 0 , 0 , fill='orange')
        draw_grid()
        draw_symbols()

    my_clear = ti.Button( root , text = """     Click here to restart game     """ , background = "green" , command = clear )
    my_clear.place(  x = round( SCREEN_WIDTH * 0.3 ) , y = round( SCREEN_HEIGHT * 0.95 )  )

    def your_choose(number):
        try:
            value=int(number.char)
            if value in range(1,10):
                N_1 = (value-1)//3
                N_2 = (value-1)%3
                if (  moves==[] or len( moves[-1] )!=1  ) and type(Playfield[N_1][N_2])==list :
                    canvas.delete('all')
                    canvas.create_rectangle( TTT_width*N_2*16/47 , TTT_height*(2-N_1)*16/47 , TTT_width*(N_2*16+15)/47 , TTT_height*((2-N_1)*16+15)/47 , fill='orange')
                    draw_grid()
                    draw_symbols()
                    moves.append([value])
                elif len( moves[-1] )==1:
                    number_block=moves[-1][0]
                    N_out_1=(number_block-1)//3
                    N_out_2=(number_block-1)%3
                    if type(Playfield[N_out_1][N_out_2])!=list : return 0
                    elif Playfield[N_out_1][N_out_2][N_1][N_2]!=2 : return 0
                    Playfield[N_out_1][N_out_2][N_1][N_2]=boool[0]
                    boool[0]= 1-boool[0]
                    moves[-1].append([value])
                    for i in range(3):
                        for j in range(3):
                            if is_full(Playfield[i][j]) and ( 1 - Is_win(Playfield[i][j]) ):
                                restart(Playfield[i][j])
                    if type(Playfield[N_1][N_2])==list and (1 - ( Is_win(Playfield[N_1][N_2]) )) :
                        if Is_win(Playfield[N_out_1][N_out_2]):
                            big_symbol=where_win(Playfield[N_out_1][N_out_2])
                            Playfield[N_out_1][N_out_2]=big_symbol
                        moves.append([value])
                        canvas.delete('all')
                        canvas.create_rectangle( TTT_width*N_2*16/47 , TTT_height*(2-N_1)*16/47 , TTT_width*(N_2*16+15)/47 , TTT_height*((2-N_1)*16+15)/47 , fill='orange')
                        draw_grid()
                        draw_symbols()
                    elif Is_win(Playfield[N_1][N_2]):
                        big_symbol=where_win(Playfield[N_1][N_2])
                        Playfield[N_1][N_2]=big_symbol
                        canvas.delete('all')
                        canvas.create_rectangle( TTT_width , TTT_height , 0 , 0 , fill='orange')
                        draw_grid()
                        draw_symbols()
                    else:
                        if Is_win(Playfield[N_out_1][N_out_2]):
                            big_symbol=where_win(Playfield[N_out_1][N_out_2])
                            Playfield[N_out_1][N_out_2]=big_symbol
                        canvas.delete('all')
                        canvas.create_rectangle( TTT_width , TTT_height , 0 , 0 , fill='orange')
                        draw_grid()
                        draw_symbols()
        finally:
            if Is_win(Playfield):
                if war.get():
                    hit=[0]
                    for i in range(3):
                        for j in range(3):
                            if 1 - ( Playfield[i][j] in [0,1] ) :
                                hit[0]=hit[0]+1
                    if boool==blue_symbol:
                        damage = ( 10 - blue_live[0] ) + hit[0]
                        life_bar_blue.create_rectangle( 0 , 0 , SCREEN_WIDTH*0.05 , round(SCREEN_HEIGHT*0.1*damage) , fill='white' )
                    else:
                        damage = ( 10 - red_live[0] ) + hit[0]
                        life_bar_red.create_rectangle( 0 , 0 , round(SCREEN_WIDTH*0.05) , round(SCREEN_HEIGHT*0.1*damage) , fill='white' )
                    for i in range(3):
                        for j in range(3): 
                            Playfield[i][j]=[[2,2,2],[2,2,2],[2,2,2]]
                    canvas.delete('all')
                    canvas.create_rectangle( TTT_width , TTT_height , 0 , 0 , fill='orange')
                    draw_grid()
                    draw_symbols()
                return "sound and Image of win"
            else:
                for block in range(9):
                    Num_1 = block//3
                    Num_2 = block%3
                    if Is_win(Playfield[Num_1][Num_2]):
                        big_symbol=where_win(Playfield[Num_1][Num_2])
                        Playfield[Num_1][Num_2]=big_symbol
    #life_bar_blue.create_rectangle( 0 , 0 , SCREEN_WIDTH*0.04 , round(SCREEN_HEIGHT*0.1*5) , fill='white' )



    root.bind("<Key>", your_choose )



























    root.mainloop()
start = ti.Button( main_menu , text = """
      Start new game      
""" , background = "blue" , command = go , fg="white")
start.place(  x = round( screen_width * 0.45 ) , y = round( screen_height * 0.05 )  )

def watch_authors():
    pass
Autorzy = ti.Button( main_menu , text = """
            Authors            
""" , background = "green" , command = watch_authors , fg="black")
Autorzy.place(  x = round( screen_width * 0.45 ) , y = round( screen_height * 0.4 )  )

    
def watch_ruls():
    pass
ruls = ti.Button( main_menu , text = """
               Rules               
""" , background = "purple" , command = watch_ruls , fg="white")
ruls.place(  x = round( screen_width * 0.45 ) , y = round( screen_height * 0.6 )  )




main_menu.mainloop()
