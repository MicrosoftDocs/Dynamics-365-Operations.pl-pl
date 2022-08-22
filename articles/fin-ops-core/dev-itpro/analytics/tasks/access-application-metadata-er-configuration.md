---
title: Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER
description: W tym artykule opisano sposób, w jaki użytkownik usługi Regulatory configuration service może zaprojektować nowe mapowanie modelu elektronicznego raportowania (ER) przy użyciu metadanych.
author: kfend
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ''
ms.openlocfilehash: 7a0947ec255a8d51f236c6c2f397378f44af1b96
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267911"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Uzyskaj dostęp do metadanych aplikacji za pomocą konfiguracji ER

[!include [banner](../../includes/banner.md)]

W następujących krokach wyjaśnimy, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) w roli Administratora Systemu lub Dewelopera elektronicznego raportowania może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych aplikacji. Dostęp do metadanych aplikacji będzie możliwy za pomocą konfiguracji metadanych ER, która zawiera przykładowy zestaw metadanych umożliwiających dostęp do transakcji handlu zagranicznego. Aby wykonać te kroki, w RCS musisz najpierw wykonać kroki podane w niniejszym artykule, [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md). Następnie wykonaj kroki opisane w artykule [Przygotowywanie metadanych aplikacji używanych w RCS](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Wymagania wstępne
1. Otwórz **Wszystkie miejsca prac** > **Electroniczne Raportowanie**. 
2. Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="import-metadata-configuration"></a>Import metadanych konfiguracji 
1. Kliknij **Konfiguracja metadanych**. 
2. Zaimportuj konfigurację metadanych ER, która zawiera metadane, które zostały skonfigurowane do generowania dokumentów elektronicznych dla handlu zagranicznego. Ta konfiguracja metadanych ER została wyeksportowana jako plik XML, podczas gdy kroki opisane w [Przygotuj metadane aplikacji do użycia w RCS](prepare-application-metadata-rcs.md) zostały wypełnione. 
3. Kliknij opcję **Wymiana**. 
4. Kliknij **Załaduj z pliku XML**. 
5. Kliknij **Przeglądaj** i wybierz plik „Handel zagraniczny metadane.xml”. 
6. Kliknij przycisk **OK**. 
7. Zamknij stronę. 

## <a name="create-data-model-configuration"></a>Stwórz model danych konfiguracji
1. Kliknij opcję **Konfiguracje raportowania**. 
2. Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe. 
3. W polu **Nazwa** wpisz "Model handlu zagranicznego". 
4. Kliknij przycisk **Utwórz konfigurację**. 
5. Kliknij przycisk **Konstruktor**. 
6. Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe. 
7. W polu **Nazwa** wpisz „Element główny”. 
8. Kliknij przycisk **Dodaj**. 
9. Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe. 
10.    W polu **Nazwa** wpisz 'Transakcje'. 
11.    W polu **Kod przedmiotu** wybierz **Lista tabel**. 
12.    Kliknij przycisk **Dodaj**. 
13.    Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe. 
14.    W polu **Nazwa** wpisz 'Kod towaru'. 
15.    W polu **Typ przedmiotu** wybierz **Ciąg**. 
16.    Kliknij przycisk **Dodaj**. 
17.    Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe. 
18.    W polu **Nazwa** wpisz "Kwota zafakturowana". 
19.    W polu **Typ przedmiotu** wybierz **Rzeczywisty**. 
20.    Kliknij przycisk **Dodaj**. 
21.    Kliknij przycisk **Nowy** aby otworzyć rozwijane okno dialogowe. 
22.    W polu **Nazwa** wpisz 'Data'. 
23.    W polu **Typ przedmiotu** wybierz **Data**. 
24.    Kliknij przycisk **Dodaj**. 
25.    Kliknij **Odniesienia do źródeł"**. 
26.    Kliknij przycisk **OK**. 
27.    Kliknij przycisk **Zapisz**. 
28.    Zamknij stronę. 
29.    Kliknij **Zmień status**. 
30.    Naciśnij **Zakończ**. 
31.    Kliknij przycisk **OK**. 

## <a name="create-model-mapping-configuration"></a>Stwórz model konfiguracji mapowania 
1. Kliknij przycisk **Utwórz konfigurację**, aby otworzyć rozwijane okno dialogowe. 
2. W polu **Nowe** wpisz "Model mapowania oparty na modelu danych Model handlu zagranicznego". 
3. W polu **Nazwa** wpisz "Mapowanie handlu zagranicznego". 
4. Kliknij przycisk **Utwórz konfigurację**. 
5. Rozwiń sekcję **Wymagania**. 
6. Kliknij przycisk **Edytuj**. 
7. Kliknij przycisk **Nowy**. 
8. Na liście oznacz wybrany wiersz. 
9. W polu **Wymagany typ komponentu** wybierz **Konfiguracja**. 
10.    Wyierz konfigurację **Metadane handlu zagranicznego**. 
11.    Kliknij przycisk **Zapisz**. 
12.    Dodaliśmy odniesienie do wersji pierwszej konfiguracji „Metadane handlu zagranicznego”. Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania. 
13.    Zamknij stronę. 
14.    Kliknij przycisk **Konstruktor**. 
15.    Kliknij przycisk **Konstruktor**. 
16.    W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**. 
17.    Kliknij **Dodaj źródło**. 
18.    W polu **Nazwa** wpisz 'Intrastat'. 
19.    Wybierz tabelę danych **Intrastat**. 
20.    Kliknij przycisk **OK**. 

> [!NOTE]
> Jedynie 2 tabele zostały zaproponowane, ponieważ tylko 2 tabele zostały dodane do zestawu metadanych, który jest aktualnie używany. 

21.    Kliknij **Powiąż**. 
22.    W widoku drzewa otwórz **Intrastat**. 
23.    W widoku drzewa wybierz **Intrastat\AmountMST**. 
24.    W widoku drzewa rozwiń **Transakcja = Intrastat**. 
25.    W widoku drzewa wybierz **Transakcja = Intrastat\Kwota zafakturowana**. 
26.    Kliknij **Powiąż**. 
27.    W widoku drzewa wybierz **Intrastat\TransDate**. 
28.    W widoku drzewa wybierz **Transakcja = Intrastat\Data**. 
29.    Kliknij **Powiąż**. 
30.    W widoku drzewa rozwiń **Intrastat\>Relacje**. 
31.    W widoku drzewa rozwiń **Intrastat\>Relacje\IntrastatCommodity**. 
32.    W widoku drzewa rozwiń **Intrastat\>Relacje\IntrastatCommodity\Kod**. 
33.    W widoku drzewa wybierz **Transakcja = Intrastat\Kod towaru**. 
34.    Kliknij **Powiąż**. 
35.    Kliknij **Potwierdź**. 

> [!NOTE]
> Udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych aplikacji, do której odwołanie znajduje się w konfiguracji metadanych ER. 
36.    Kliknij przycisk **Zapisz**. 
37.    Zamknij stronę. 
38.    Zamknij stronę. 
39.    W razie potrzeby można rozszerzyć istniejący zbiór metadanych, a następnie wyeksportować nową skompletowaną wersję konfiguracji metadanych programu ER Następnie można zaimportować ją do RCS i zaktualizować wymagania wstępne skonfigurowanego mapowania modeli odnosząc się do nowej wersji zaimportowanej konfiguracji metadanych. 

> [!NOTE]
> Ten sposób uzyskiwania informacji o metadanych aplikacji jest jedynym dostępnym dla aplikacji wdrażanych lokalnie (w przypadku gdy używany jest lokalny model danych biznesowych (LBD) lub lokalny model wdrażania).
        


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
