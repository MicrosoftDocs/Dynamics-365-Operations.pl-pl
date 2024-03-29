---
title: Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji
description: Kroki w tym artykule wyjaśniają, w jaki sposób użytkownik usługi Regulatory configuration service może zaprojektować nowe mapowanie modelu elektronicznego raportowania (ER) przy użyciu metadanych.
author: kfend
ms.date: 06/29/2019
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
ms.openlocfilehash: 1a935b96e247978fc2b2f9449d403c92bff35f17
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267881"
---
# <a name="access-application-metadata-by-using-connected-applications"></a>Uzyskaj dostęp do metadanych aplikacji za pomocą połączonych aplikacji

[!include [banner](../../includes/banner.md)]

W następujących krokach wyjaśnimy, w jaki sposób użytkownik usługi Regulatory configuration service (RCS) w roli Administratora Systemu lub Dewelopera elektronicznego raportowania może zaprojektować nowe mapowanie modelu Elektronicznego raportowania (ER) przy użyciu metadanych w aplikacji finansowych i operacyjnych. Metadane aplikacji będą dostępne online za pomocą aplikacji połączonej z RCS. Przykładowe mapowanie modelu ER zostanie skonfigurowane do dostępu do transakcji handlu zagranicznego. Aby wykonać te kroki, w RCS należy najpierw wykonać kroki w artykule [Tworzenie dostawców konfiguracji i oznacz je jako aktywne](er-configuration-provider-mark-it-active-2016-11.md). Jeśli nie wykonano wszystkich podanych kroków w artykule [Dostęp do metadanych aplikacji przy użyciu konfiguracji ER](access-application-metadata-er-configuration.md), pobierz [Przykłady elektronicznego raportowania](https://download.microsoft.com/download/0/4/e/04e13839-e423-442b-a6c2-dd35b1045c2d/Dynamics%20365%20for%20Finance%20and%20Operations%208.1%20Electronic%20reporting%20task%20guides.zip) i zapisz następujące konfiguracje ER: Handel zagraniczny metadane.xml; Model handlu zagranicznego.xml; Mapowanie handlu zagranicznego.xml, a następnie wykonaj kroki procedury.

## <a name="prerequisites"></a>Wymagania wstępne
1. Otwórz **Wszystkie miejsca prac** > **Elektroniczne Raportowanie**. 
2. Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="get-required-er-configurations"></a>Uzyskaj wymagane konfiguracje ER
1. Kliknij opcję **Konfiguracje raportowania**. 
2. Jeśli wykonałeś już kroki w procedurze [Uzyskaj dostęp do metadanych aplikacji przy użyciu konfiguracji ER](access-application-metadata-er-configuration.md) i masz już wszystkie niezbędne konfiguracje ER (metadane handlu zagranicznego, model i konfiguracje mapowania) w bieżącej instancji RCS. Możesz pominąć wszystkie pozostałe kroki tego zadania podrzędnego. 
3. Kliknij **Zmień** 
4. Kliknij **Załaduj z pliku XML**. 
5. Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny metadane.xml**. 
6. Kliknij przycisk **OK**. 
7. Kliknij **Zmień** 
8. Kliknij **Załaduj z pliku XML**. 
9. Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny model.xml**. 
10. Kliknij przycisk **OK**. 
11. Kliknij **Zmień** 
12. Kliknij **Załaduj z pliku XML**. 
13. Kliknij **Przeglądaj** i wybierz plik **Handel zagraniczny mapowanie.xml**. 
14. Kliknij przycisk **OK**. 

## <a name="register-a-connected-application"></a>Zarejestruj połączoną aplikację
1. Zamknij stronę. 
2. Zamknij stronę. 
3. Otwórz **Wszystkie miejsca prac** > **Elektroniczne Raportowanie**. 
4. Kliknij **Połączone aplikacje**. 
5. Upewnij się, że skonfigurowana aplikacja jest oparta na Azure i dostępna dla bieżącego użytkownika RCS. Wymagane jest również, aby bieżący użytkownik RCS miał dostęp do wybranej aplikacji i został zarejestrowany jako jej użytkownik z rolą dającą mu uprawnienia dostępu do metadanych aplikacji. 
6. Kliknij przycisk **Nowy**. 
7. W polu **Nazwa** wpisz 'MyConnectedApp'. 
8. W polu **Aplikacja** wpisz 'https:// mycompany.operations.dynamics.com'. 
9. W polu **Dzierżawca** wpisz „mycompany.onmicrosoft.com”. 
10. Kliknij przycisk **Zapisz**. 
11. Po sprawdzeniu połączenia ze skonfigurowaną aplikacją na stronie **Połącz ze zdalną aplikacją** kliknij link **Kliknij tutaj, aby połączyć się z wybraną aplikacją zdalną**. 
12. Kliknij **Sprawdź połączenie**. 
13. Kliknij przycisk **Zamknij**. 
14. Gdy sprawdzenie poprawności połączenia powiedzie się, szczegóły wersji i dzierżawcy zostaną zaktualizowane dla skonfigurowanej aplikacji w bieżącej sieci. 

## <a name="review-existing-model-mapping-configuration"></a>Przejrzyj istniejącą konfigurację mapowania modelu
1. Zamknij stronę. 
2. Kliknij opcję **Konfiguracje raportowania**. 
3. W widoku drzewa otwórz **Model handlu zagranicznego**. 
4. W widoku drzewa wybierz **Model handlu zagranicznego\Handel zagraniczny mapowanie**. 
5. Rozwiń sekcję **Wymagania**. 

    > [!NOTE]
    > Obecnie to mapowanie odnosi się do konfiguracji metadanych. Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania. 

6. Kliknij przycisk **Konstruktor**. 
7. Kliknij przycisk **Konstruktor**. 
8. W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**. 
9. Kliknij **Dodaj źródło**. 
10. W polu **Tabela** wpisz wartość. 

    > [!NOTE]
    > Obecnie to mapowanie odnosi się do konfiguracji metadanych. Metadane aplikacji z tej konfiguracji będą proponowane podczas projektowania tego modelu mapowania. 

11. Kliknij **Anuluj**. 
12. Zamknij stronę. 
13. Zamknij stronę. 

## <a name="assign-connected-application-to-model-mapping"></a>Przypisz podłączoną aplikację do mapowania modelu 
1. Kliknij przycisk **Edytuj**. 
2. Wybierz aplikację **MyConnectedApp**. 

    > [!NOTE]
    > Obecnie to mapowanie odnosi się do metadanych wybranej połączonej aplikacji. Gdy to samo mapowanie odnosi się do konfiguracji metadanych i połączonej aplikacji w tym samym czasie, zostaną użyte metadane połączonej aplikacji. 

3. Kliknij przycisk **Konstruktor**. 
4. Kliknij przycisk **Konstruktor**. 
5. W widoku drzewa wybierz **Dynamics 365 for Operations\Dane tabeli**. 
6. Kliknij **Dodaj źródło**. 
7. W polu **Tabela** wpisz wartość. 

    > [!NOTE]
    > Zaproponowano więcej niż dwie tabele aplikacji, ponieważ to mapowanie wykorzystuje wszystkie metadane połączonej aplikacji, która została do niej przypisana. 

8. Kliknij **Anuluj**. 
9. Kliknij **Potwierdź**. 

    > [!NOTE]
    > Udało nam się powiązać elementy modelu danych z elementami źródeł danych opisanymi przy użyciu szczegółów metadanych połączonej aplikacji, która została przypisana do tego mapowania. 

10. Zamknij stronę. 
11. Zamknij stronę. 

Gdy trzeba ocenić ten model mapowania przy użyciu metadanych innej wersji aplikacji, zarejestruj inną połączoną aplikację, przypisz ją do tego mapowania modelu i sprawdź poprawność względem nowych metadanych.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

