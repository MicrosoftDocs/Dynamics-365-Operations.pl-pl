---
title: Wybieranie definicji modeli danych podczas tworzenia formatów
description: Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc357db8acbdb98741a694a8a9d3c0c0625c50e4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551096"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a>Wybieranie definicji modeli danych podczas tworzenia formatów

[!include [task guide banner](../../includes/task-guide-banner.md)]

Aby wykonać kroki podane w tej procedurze, należy najpierw wykonać procedurę ER Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego. 

W tej procedurze pokazano, jak można wybrać pozycję główną modelu jako definicję modelu danych w celu wstawienia konfiguracji formatu raportowania elektronicznego (ER) przeznaczonej do generowania dokumentów elektronicznych. W tej procedurze dodasz nową konfigurację formatu ER dla przykładowej firmy „Litware, Inc.”. 

Ta procedura jest przeznaczona dla użytkowników z przypisaną rola Administrator systemu lub Deweloper raportowania elektronicznego. Kroki można wykonać przy użyciu dowolnego zestawu danych.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca konfiguracji przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako Aktywny. Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj procedurę Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego.  
2. Kliknij opcję Konfiguracje raportowania.

## <a name="add-a-new-er-data-model-configuration"></a>Dodawanie nowej konfiguracji modelu danych ER
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
    * Dodaliśmy nową konfigurację modelu raportowania elektronicznego zawierającą model danych, który jest przeznaczony do używania jako źródło danych do generowania raportów ER.  
2. W polu Nazwa wpisz „Model płatności (fikcyjny)”.
    * Model płatności (fikcyjny)  
3. Kliknij przycisk Utwórz konfigurację.
4. Kliknij przycisk Konstruktor.
    * Otwórz projektanta ER w celu określenia struktury modelu danych tej konfiguracji.  
    * Załóżmy, że projektujemy model danych dla dziedziny płatności biznesowych do obsługi 2 metod płatności — polecenia przelewu i polecenia zapłaty.  
5. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
6. W polu Nazwa wpisz „Płatności — polecenie przelewu”.
    * Płatności — polecenie przelewu  
7. Kliknij przycisk Dodaj.
8. Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.
9. W polu Nowy węzeł jako wpisz „Element główny modelu”.
10. W polu Nazwa wpisz „Płatności — polecenie zapłaty”.
    * Płatności — polecenie zapłaty  
11. Kliknij przycisk Dodaj.
12. Kliknij przycisk Zapisz.
13. Zamknij stronę.
14. Kliknij przycisk Zmień stan.
    * Wykonaj wersję roboczą modelu, tak aby była dostępna w mapowaniach i formatach nowego modelu.  
15. Kliknij przycisk Wykonaj.
16. Kliknij przycisk OK.

## <a name="start-to-enter-a-new-er-format-configuration"></a>Rozpoczynanie wprowadzania nowej konfiguracji formatu ER
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
2. W polu Nowy wpisz „Format oparty na modelu danych Model płatności (fikcyjny)”.
3. W polu Definicja modelu danych wprowadź lub wybierz wartość.
    * Należy zwrócić uwagę, że wszystkie pozycje główne wybranego modelu danych są obecnie dostępne do wyboru jako definicja modelu danych. Można kontynuować projektowanie formatu przy użyciu dowolnych potrzebnych pozycji głównych modelu danych. Brak mapowania modelu dla wybranej pozycji głównej nie uniemożliwia kontynuowania.  
4. Zamknij stronę.

## <a name="add-a-new-er-model-mapping-configuration"></a>Dodawanie nowej konfiguracji mapowania modelu ER
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
2. W polu Nowy wpisz „Mapowanie modelu oparte na modelu danych Model płatności (fikcyjny)”.
3. W polu Nazwa wpisz „Mapowania modelu płatności (fikcyjnego)”.
    * Mapowania modelu płatności (fikcyjnego)  
4. W polu Definicja modelu danych wprowadź lub wybierz wartość.
5. Kliknij przycisk Utwórz konfigurację.

## <a name="design-er-model-mappings"></a>Projektowanie mapowań modeli ER
1. Kliknij przycisk Konstruktor.
    * Za pomocą projektanta ER określ mapowania modelu dla wymaganych pozycji głównych.  
2. Kliknij przycisk Konstruktor.
    * Wykonaj symulację skonfigurowania mapowania wybranego modelu na pozycję główną wybranego modelu.  
3. W drzewie zaznacz element „Dynamics 365 for Operations\Rekordy w tabeli”.
4. Kliknij opcję Dodaj element główny.
5. W polu Nazwa wprowadź „Księga”.
6. W polu Tabela wpisz „LedgerJournalTrans”.
    * LedgerJournalTrans  
7. Kliknij przycisk OK.
8. Kliknij przycisk Zapisz.
9. Zamknij stronę.
10. Zamknij stronę.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Rozpoczynanie wprowadzania następnej nowej konfiguracji formatu ER
1. W drzewie zaznacz element „Model płatności (fikcyjny)”.
2. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
3. W polu Nowy wpisz „Format oparty na modelu danych Model płatności (fikcyjny)”.
4. W polu Definicja modelu danych wprowadź lub wybierz wartość.
    * Należy zauważyć, że teraz tylko jedna pozycja główna jest dostępna do mapowania źródeł danych aplikacji. Podczas wprowadzania jednego lub więcej mapowań modeli tylko pozycje głównego modelu, które są mapowane na źródła danych aplikacji, mogą być wybierane jako definicja modelu podczas dodawania formatu raportowania elektronicznego.   
5. Zamknij stronę.

