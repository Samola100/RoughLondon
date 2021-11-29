get_started = 'get started'
tube_or_bus = 'tube_or_bus'

tube_story = 'tube_story'
stand_or_sit = 'stand_or_sit'
sit_death = 'sit_death'
stand_story = 'stand_story'
join_riot_story = 'join riot story'
join_riot_or_carry_on = 'join_riot_or_carry on'
riot_death = 'riot death'
save_mp_or_leave_him = 'save_mp_or_leave him'
save_mp_death = 'save_mp_death'
let_mp_die_story = 'let_mp_die_story'
estate_park_or_westfield = 'estate_park_or_westfield'
estate_death = 'estate_death'
westfield_story = 'westfield_story'

bus_story = 'bus_story'
upstairs_or_downstairs = 'upstairs_or_downstairs'
downstairs_story = 'downstairs_story'
upstairs_death = 'upstairs_death'
walk_or_cab = 'walk_or_cab'
cab_death = 'cab_death'
walk_story = 'walk_story'
park_or_main_road_or_alley = 'park_or_main_road_or_alley'
main_road_death = 'main_road_death'
park_death = 'park_death'
alley_story = 'alley_story'

bouncer_story = 'bouncer story'
fight_beg_or_run_past = 'fight_beg_or_run_past'
run_past_death = 'run_past_death'
beg_death = 'beg_death'
fight_bouncer_story = 'fight_bouncer_story'

you_are_in = 'you_are_in'


def play_again():
    print('Do you want to play again, fam?')
    answer10 = input('>').lower()
    if 'yes' or 'y' in answer10:
        game_opener()
    else:
        exit()


def win():
    print(f'{you_are_in}')


def come_again():
    print('Wasteman Kant Spel!!!! Try righting dat agian!')


def bouncer():
    print(f'{bouncer_story}')
    print(f'{fight_beg_or_run_past}')
    answer9 = input('>').lower()
    if 'fight' in answer9:
        print(f'{fight_bouncer_story}')
        win()
        play_again()
    elif 'run' or 'past' in answer9:
        print(f'{run_past_death}')
        play_again()
    elif 'beg' in answer9:
        print(f'{beg_death}')
        play_again()
    else:
        come_again()
        bouncer()


def parkmainalley():
    print(f'{park_or_main_road_or_alley}')
    answer8 = input('>').lower()
    if 'park' in answer8:
        print(f'{park_death}')
        play_again()
    elif 'main' or 'road' in answer8:
        print(f'{main_road_death}')
        play_again()
    elif 'alley' in answer8:
        print(f'{alley_story}')
        bouncer()
    else:
        come_again()
        parkmainalley()


def walkcab():
    print(f'{walk_or_cab}')
    answer7 = input('>').lower()
    if 'cab' in answer7:
        print(f'{cab_death}')
        play_again()
    elif 'walk' in answer7:
        print(f'{walk_story}')
        parkmainalley()
    else:
        come_again()
        walkcab()


def bus():
    print(f'{bus_story}')
    print(f'{upstairs_or_downstairs}')
    answer6 = input('>').lower()
    if 'upstairs' in answer6:
        print(f'{upstairs_death}')
        play_again()
    elif 'downstairs' in answer6:
        print(f'{downstairs_story}')
        walkcab()
    else:
        come_again()
        bus()


def estwestpark():
    print(f'{estate_park_or_westfield}')
    answer5 = input('>').lower()
    if 'park' in answer5:
        print(f'{park_death}')
        play_again()
    elif 'estate' in answer5:
        print(f'{estate_death}')
        play_again()
    elif 'westfield' in answer5:
        print(f'{westfield_story}')
        bouncer()
    else:
        come_again()
        estwestpark()


def mp():
    print(f'{save_mp_or_leave_him}')
    answer4 = input('>').lower()
    if 'save' in answer4:
        print(f'{save_mp_death}')
        play_again()
    elif 'leave' or 'him' in answer4:
        print(f'{let_mp_die_story}')
        estwestpark()
    else:
        come_again()
        mp()


def riot():
    print(f'{join_riot_or_carry_on}')
    answer3 = input('>').lower()
    if 'join' or 'riot' in answer3:
        print(f'{join_riot_story}')
        mp()
    elif 'carry' or 'on' in answer3:
        print(f'{riot_death}')
        play_again()
    else:
        come_again()
        riot()


def tube():
    print(f'{tube_story}')
    print(f'{stand_or_sit}')
    answer2 = input('>').lower()
    if 'sit' in answer2:
        print(f'{sit_death}')
        play_again()
    elif 'stand' in answer2:
        print(f'{stand_story}')
        riot()
    else:
        come_again()
        tube()


def game_opener():
    print(f'{get_started}')
    print(f'{tube_or_bus}')
    answer1 = input('>').lower()
    if 'tube' in answer1:
        tube()
    elif 'bus' in answer1:
        bus()
    else:
        come_again()
        game_opener()


game_opener()

