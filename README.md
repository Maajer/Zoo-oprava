# Zoo-oprava
# Počty zvířat v zoo
tygri = 0
lvy = 0
opice = 0  
# Funkce pro přidání zvířat
def pridej(zvire, pocet):
    global tygri, lvy, opice
    if zvire == "tygri":
        tygri += pocet
    elif zvire == "lvy":
        lvy += pocet
    elif zvire == "opice":
        opice += pocet
    else:
        print("Něco si zadal špatně")
# Funkce pro odebrání zvířat  
def odeber(zvire, pocet):
    global tygri, lvy, opice
    if zvire == "tygri" and pocet <= tygri:
        tygri -= pocet
    elif zvire == "lvy" and pocet <= lvy:
        lvy -= pocet
    elif zvire == "opice" and pocet <= opice:
        opice -= pocet
    else:
        print("Něco si zadal špatně")
# Funkce pro výpis počtu zvířat
def vypis():
    print(f"Tygři: {tygri}")
    print(f"Lvi: {lvy}")
    print(f"Opice: {opice}")

opakovat = "ano"

while(opakovat=="ano"):

    # výpis akcí co lze provádět 
    print("Vyberte jednu z akcí(pište pouze číslo): ")
    print("1. přidat zvíře")
    print("2. odebrat zvíře")
    print("3. vypsat seznam zvířat")

    # načtení akce od uživatele
    cislo = int(input())
    
    # Jednotlivá načtení potřebných informací a volání funkce
    if cislo == 1:
        zvire = input("Zadejte zvířata která chcete přidat (tygri, lvy, opice): ")
        pocet = int(input("Zadejte počet těchto zvířat: "))
        pridej(zvire, pocet)
    elif cislo == 2:
        zvire = input("Zadejte zvířata která chcete odebrat (tygri, lvy, opice): ")
        pocet = int(input("Zadejte počet těchto zvířat: "))
        odeber(zvire, pocet)
    elif cislo == 3:
        vypis()

    # update proměnné opakovat, aby nedošlo k zacyklení programu
    opakovat = input("Chcete opakovat program? (ano/ne): ")
