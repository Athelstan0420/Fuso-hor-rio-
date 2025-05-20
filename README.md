# Fuso-horario

    """
    Trabalhar com datas e horas.
    
    -> Biblioteca: datetime
    
    """ 
    #=================================================================================================
    from datetime import *
    texto_data = "08/04/2025 01:52"
    minha_data = datetime.strptime(texto_data, "%d/%m/%Y %H:%M") # Pega uma data/hora e transforma em texto;
    print(minha_data)
    #=================================================================================================
    import pytz #Python timezone => tornar qqr data ciente do local dela. 
    # para saber qual sigla utilizar pesquise: "https://en.wikipedia.org/wiki/List_of_tz_database_time_zones"
    fuso_horario = pytz.timezone("America/Sao_Paulo") #UTC -> padrão 00h
    minha_data_com_fuso = fuso_horario.localize(minha_data) #dada minhda posição de greenwich
    print(minha_data_com_fuso)#Diz qual o fuso horário que voce está.
    #=================================================================================================
    novo_fuso = pytz.timezone("Europe/Paris")
    minha_data_novo_fuso = minha_data_com_fuso.astimezone(novo_fuso)#Traduzindo seu fuso para um novo fuso de outro local;
    print(minha_data_novo_fuso)
    #=================================================================================================
    print(minha_data_novo_fuso.dst()) # Para saber se está em horário de verão
    
