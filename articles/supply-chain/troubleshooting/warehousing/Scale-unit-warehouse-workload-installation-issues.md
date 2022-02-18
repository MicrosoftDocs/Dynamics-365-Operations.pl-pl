---
title: Problemy z przetwarzaniem występują po zainstalowaniu pracy magazynu jednostek skalowania
description: Ten temat opisuje problemy, które mogą wystąpić wkrótce po zainstalowaniu obciążenia magazynu wagi i podaje rady, jak je rozwiązać.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071655"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>Problemy z przetwarzaniem występują po zainstalowaniu pracy magazynu jednostek skalowania

Ten temat opisuje problemy, które mogą wystąpić wkrótce po zainstalowaniu obciążenia magazynu wagi i podaje rady, jak je rozwiązać.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>Problem 1: Błąd po uwolnieniu ładunku z poziomu warsztatu planowania ładunków

### <a name="symptoms-of-issue-1"></a>Objawy problemu 1

Kiedy uwalniasz ładunek ze strony **Pracowni planowania ładunków** lub **Pracowni planowania ładunków wychodzących**, otrzymujesz wiadomość o błędzie, która ma następującą postać:

> Przechwycono wyjątek podczas księgowania ładunku %1. Nie można zwolnić ładunku.
> 
> UPDATE WHSSHIPMENTTABLE SET ...
> 
> Nie można edytować rekordu w tabeli Wysyłki (WHSShipmentTable). Identyfikator wysyłki: ...

Oto rzeczywisty przykład, który zawiera przykładowe dane:

> Przechwycono wyjątek podczas księgowania ładunku USMF-000033. Nie można zwolnić ładunku.
sesja 5133 (administrator)
>
> UPDATE WHSSHIPMENTTABLE SET ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? WHERE ((RECID=?) AND (RECVERSION=?))  
> [Microsoft][ODBC Driver 17 dla SQL Server][SQL Server]Scale Unit @@ próbuje zaktualizować rekordy należące do Scale Unit @A.  
> Serwer obiektów Azure:
>
> Nie można edytować rekordu w tabeli Wysyłki (WHSShipmentTable). Identyfikator wysyłki: USMF-000031, USMF-000033. Baza SQL zgłosiła błąd:

### <a name="cause-of-issue-1"></a>Przyczyna problemu nr 1

Ten problem może wystąpić, jeśli podczas instalacji obciążenia magazynu wagi zaistnieje następująca kombinacja warunków:

- System zawiera niezwolniony ładunek, w którym wiele linii jest powiązanych z różnymi zamówieniami, a niektóre linie ładunku nie są powiązane z przesyłką.
- System jest skonfigurowany tak, aby korzystać z konsolidacji przesyłek.

W rozmieszczeniu rozproszonej topologii hybrydowej każdy rekord ładunku i przesyłki jest oznaczony jako należący do konkretnej jednostki wagi lub węzła. Kiedy uwalniasz ładunek ze strony **Pracowni planowania ładunków**, system zmienia przypisaną mu własność. Jednak z powodu wcześniej wymienionych warunków system może nie być w stanie rozwiązać problemu własności danych. Dlatego nie udaje się uwolnić ładunku do magazynu.

### <a name="resolution-of-issue-1"></a>Rozwiązanie problemu 1

Podziel ładunek na dwa mniejsze zanim wydasz go do magazynu.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>Problem 2: Błąd podczas przetwarzania grupy czynności na jednostce skalowania

### <a name="symptoms-of-issue-2"></a>Objawy problemu 2

Kiedy przetwarzasz falę na jednostce skalowania, otrzymujesz komunikat o błędzie, który ma następującą postać:

> Nie możesz zmodyfikować wiersza obciążenia z RecId = %1, load id= %2, ponieważ nadal jest on własnością węzła przedsiębiorstwa. Upewnij się, że odpowiedni ładunek wychodzący został zwolniony do jednostki wagi i tym samym zostały utworzone linie zleceń magazynowych.

Oto rzeczywisty przykład, który zawiera przykładowe dane:

> Dziennik informacyjny dla zadania Execute Wave USMF-000000012 (9223377668365210)  
> Dziennik informacyjny dla zadania Execute Wave USMF-000000012 (9223377668370462)  
> Nie możesz zmodyfikować wiersza obciążenia z RecId = 68719478242, load id= USMF-000034, ponieważ nadal jest on własnością węzła przedsiębiorstwa. Upewnij się, że odpowiedni ładunek wychodzący został zwolniony do jednostki wagi i tym samym zostały utworzone linie zleceń magazynowych.

### <a name="cause-of-issue-2"></a>Przyczyna problemu nr 2

W rozmieszczeniu rozproszonej topologii hybrydowej własność danych o ładunkach i przesyłkach jest przypisana do konkretnej jednostki wagowej lub węzła. Oczekuje się, że w ramach przetwarzania falowego własność danych zostanie przypisana do jednostki wagowej.

Kiedy instalujesz obciążenie magazynu jednostki wagi, jeśli otwarta przesyłka jest powiązana z ładunkiem i falą, system nie może kontrolować własności danych. Dlatego przetwarzanie fal nie powiedzie się na jednostce skalowania.

### <a name="resolution-of-issue-2"></a>Rozwiązanie problemu 2

Zwalnianie ładunku do magazynu z centrum.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>Rozwiązywanie problemów poprzez przeglądanie własności i przeznaczenia rekordu

W rozproszonej topologii hybrydowej wiele typów rekordów jest oznaczonych jako należące do konkretnej jednostki wagowej lub węzła. Gdy przełączysz się na rozproszoną topologię hybrydową i/lub skonfigurujesz nowe obciążenie magazynu jednostek skalarnych, system przypisze własność do każdego odpowiedniego rekordu. Ten proces może czasem powodować błędy lub nieoczekiwane rezultaty. Dlatego informacje o własności rekordu i miejscu docelowym transferu mogą pomóc ci w rozwiązywaniu problemów, które pojawiają się po wprowadzeniu tego typu zmian.

Wykonaj poniższe kroki, aby zobaczyć własność i miejsce docelowe transferu dla danego rekordu.

1. Otwórz odpowiedni rekord.
1. W okienku akcji na karcie **Opcje** w grupie **Informacje o rekordzie** wybierz opcję **Pokaż wszystkie pola**.
1. Strona, która się pojawi, pokazuje wartości dla wszystkich pól, które są dostępne dla wybranego rekordu. Sprawdź następujące pola:

    - **SYSSCALEUNITID** — w tym polu jest przedstawiany bieżący właściciel rekordu.
    - **SYSTARGETSCALEUNITID** — w tym polu jest przedstawiany identyfikator jednostki skalowania centrum lub jednostki skalowania, do których rekord zostanie przeniesiony po zakończeniu pracy z nim przez bieżącego właściciela. Wartość tego pola jest używana przez zadania wsadowe, które zarządzają tym typem procesu. Chociaż to pole nie jest bezpośrednio związane z własnością, własność może się zmienić, gdy rekord jest przenoszony. W niektórych przypadkach pole to będzie puste.
