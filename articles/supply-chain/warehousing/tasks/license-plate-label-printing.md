---
title: Włączanie drukowania etykiet numeru identyfikacyjnego
description: Ten temat pokazuje, jak włączyć automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e548e5e5528733412d47478dd740b87217cdac2
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016109"
---
# <a name="enable-license-plate-label-printing"></a>Włączanie drukowania etykiet numeru identyfikacyjnego

[!include [banner](../../includes/banner.md)]

Ten temat pokazuje, jak włączyć automatyczne drukowanie etykiety z numerem seryjnym kontenera wysyłkowego (SSCC) po pobraniu ostatniego towaru z magazynu w procesie pracy pobierania dla sprzedaży. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Jeśli wykonujesz procedurę przy użyciu własnych danych, trzeba mieć zdefiniowaną sekwencję numeracji dla numerów identyfikacyjnych. Przed rozpoczęciem tego zadania należy skonfigurować drukarkę etykiet. Wybierz kolejno opcje Administrowanie organizacją > Ustawienia > Drukarki sieciowe. W okienku akcji kliknij przycisk Opcje, a następnie kliknij przycisk Pobierz instalatora agenta rozsyłania dokumentów. Uruchom instalatora i przed rozpoczęciem procedury upewnij się, że działająca drukarka sieciowa ma ustawiony status Aktywna.


## <a name="set-up-the-gs1-company-prefix"></a>Konfigurowanie prefiksu GS1 firmy
1. Otwórz **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**.
2. W polu **Prefiks GS1 firmy** wprowadź 7-cyfrowy numer GS1 firmy.
3. Wybierz opcję **Zapisz**.
4. Zamknij stronę.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Konfigurowanie sekwencji numeracji w numerze identyfikacyjnym SSCC
1. Otwórz **Okienko nawigacji > Moduły > Administrowanie organizacją > Sekwencje numerów > Sekwencje numerów**.
2. W polu **Obszar** wybierz opcję.
3. W polu **Odwołanie** wybierz opcję.
4. W polu **Firma** wpisz wartość.
5. Rozwiń sekcję **Segmenty**.
6. Wybierz opcję **Edycja**.
7. W tabeli **segmenty** zaznacz pierwszy wiersz.
8. Wybierz **Usuń**.
9. Wybierz **Usuń**.
10. Wybierz opcję **Zapisz**.
11. Zamknij stronę.

## <a name="create-the-document-route-layout"></a>Tworzenie układu trasy dokumentów
1. Wybierz kolejno **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Wybór trasy dokumentów > Układy wyboru trasy dokumentów**. Włącz układ kodu SSCC.  
2. Wybierz pozycję **Nowy**.
3. W polu **Identyfikator układu** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. Wybierz **Wstaw na końcu tekstu**.
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę.

## <a name="set-up-the-document-routing"></a>Konfigurowanie opcji wyboru trasy dokumentów
1. Wybierz kolejno **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Wybór trasy dokumentów > Wybór trasy dokumentów**.
2. W polu **Typ zlecenia pracy** wybierz opcję.
3. Wybierz pozycję **Nowy**.
4. W polu **Magazyn** wpisz wartość.
5. W polu **Nazwa** wpisz wartość.
6. Wybierz pozycję **Nowy**.
7. W polu **Identyfikator układu** wprowadź lub wybierz wartość.
8. W polu **Nazwa** wpisz nazwę drukarki, której chcesz używać.
9. Wybierz opcję **Zapisz**.
10. Zamknij stronę.

## <a name="create-mobile-device-menu"></a>Utwórz menu urządzenia przenośnego
1. Wybierz **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa elementu menu** wpisz wartość.
4. W polu **Tytuł** wpisz wartość.
5. W polu **Tryb** wybierz opcję.
6. W polu **Użyj istniejącej pracy** zaznacz opcję **Tak**.
7. W polu **Generuj numer identyfikacyjny** zaznacz opcję **Tak**.
8. Rozwiń sekcję **Klasy robocze**.
9. Wybierz pozycję **Nowy**.
10. W polu **Identyfikator klasy roboczej** wpisz wartość.
11. Wybierz opcję **Zapisz**.
12. Zamknij stronę.
13. Wybierz **okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.
14. W widoku drzewa zaznacz element menu, który został wcześniej utworzony.
15. Wybierz opcję **Edycja**.
16. Wybierz strzałkę, aby dodać element menu do menu.
17. Wybierz opcję **Zapisz**.
18. Zamknij stronę.

## <a name="update-a-work-template"></a>Aktualizacja szablonu pracy
1. Przejdź do **Okienko nawigacji > Moduły > Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy**.
2. Wybierz opcję **Edycja**.
3. Wybierz pozycję **Nowy**.
4. W polu **Typ pracy** zaznacz opcję **Drukowanie**.
5. W polu **Identyfikator klasy roboczej** wprowadź lub wybierz wartość.
6. Wybierz **Przenieś w górę**.
7. Wybierz opcję **Zapisz**.
8. Zamknij stronę.

