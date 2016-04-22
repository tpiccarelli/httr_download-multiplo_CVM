# httr_download-multiplo_CVM
# CVM download múltiplo

#Opção 1:
    # Instruções:
    # http://sistemas.cvm.gov.br/Port/DownloadArqs/download02.htm
    
    # Aceessa sistema CVM:
    sist_cvm <- "https://www.rad.cvm.gov.br/DOWNLOAD/SolicitaDownload.asp"
    
    # Dados acesso:
    login <- list(txtLogin = "397DWLTPB", txtSenha = "petrobR0", txtData = "15/04/2015", txtHora = "00:00", txtDocumento = "4")
    
    # Carrega package "httr":
    library(httr)
    
    # Comando de acesso:
    set_config(config(ssl_verifypeer = 0L))
    acesso <- POST(url=sist_cvm, body=login, encode="multipart", verbose())

# Opção 2:
    # Dica StackOverflow:
    cvm <- "https://WWW.RAD.CVM.GOV.BR/DOWNLOAD/SolicitaDownload.asp"
    
    informs <- list(txtLogin = "397DWLTPB", 
                    txtSenha = "petrobR0", 
                    txtData = format(Sys.Date(), "%d/%m/%Y"), 
                    txtHora = "00:00", 
                    txtDocumento = "TODOS")
    
    set_config(config(ssl_verifypeer = 0L))
    
    acesso <- POST(url = cvm, 
                   body = informs, 
                   encode = "form", 
                   verbose())
