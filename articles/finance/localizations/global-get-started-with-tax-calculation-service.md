---
title: Rozpoczynanie pracy z obliczaniem podatku
description: W tym temacie wyjaśniono, jak skonfigurować obliczanie podatku.
author: wangchen
ms.date: 05/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e72b81d4a109db2dd8b4c6ca2ca0b030220e25f3
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216726"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Zacznij od obliczania podatku (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ten temat zawiera informacje dotyczące sposobu rozpoczęcia pracy z obliczaniem podatku. Po pierwsze przeprowadzi użytkownika przez etapy konfiguracji Microsoft Dynamics Lifecycle Services (usługi LCS), Regulatory Configuration Services (RCS) Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Następnie przegląda wspólny proces korzystania z funkcji obliczania podatków w transakcjach zarządzania Finance i Supply Chain Management.

Ta konfiguracja składa się z następujących czterech kroków:

1. W LCS zainstaluj obliczanie podatku.
2. W RCS należy skonfigurować funkcję obliczania podatku. Te dane konfiguracyjne nie są specyficzne dla pojedynczej firmy. Można je udostępnić innym podmiotom prawnym w zarządzaniu Finance i Supply Chain Management.
3. W Finance i Supply Chain Management dostaw skonfiguruj parametry obliczania podatku według firmy.
4. W programie Finance and Supply Chain Management utwórz transakcje, takie jak zamówienia sprzedaży, i użyj funkcji Obliczanie podatku do określania i obliczania podatków.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione następujące wymagania wstępne:

- Masz dostęp do swojego konta usługi LCS i wdrożono projekt usługi LCS w środowisku warstwy 2 (lub powyżej), w którym jest uruchomiona wersja Dynamics 365 10.0.18 z [KB4616360](https://fix.lcs.dynamics.com/Issue/Details?kb=4616360&bugId=568738&dbType=3&qc=1f1c04ff39adad74ef871f539e8d73e14c1893ef7cc4b6e3f7d5c5864ec2781a) lub nowsza.
- Masz dostęp do swojego konta usługi RCS.
- Skontaktujemy się z firmą Microsoft w celu włączenia lotowania w wdrożonym środowisku Finance i Supply Chain Management.

## <a name="set-up-tax-calculation-in-lcs"></a>Skonfiguruj obliczanie podatku w LCS

1. Zaloguj się w rozwiązaniu [LCS](https://lcs.dynamics.com)
2. Ukończ konfigurację integracji Microsoft Power Platform. Aby uzyskać więcej informacji, zobacz [Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Wybierz jedno ze wdrożonych środowisk nieprodukcji, a następnie wybierz opcję **Zainstaluj nowy dodatek**.
4. Wybierz opcję **Obliczanie podatku (wersja zapoznawcza)**.
5. Przeczytaj i przyjmij warunki i postanowienia, a następnie wybierz opcję **Zainstaluj**.

## <a name="set-up-tax-calculation-in-rcs"></a>Skonfiguruj obliczanie podatku w RCS

Kroki w tej sekcji nie są powiązane z określoną firmą. Tę procedurę należy wykonać tylko jeden raz i można ją wykonać w dowolnej firmie w RCS.

1. Zaloguj się w [RCS](https://marketing.configure.global.dynamics.com/).
2. W obszarze roboczym **Raportowanie elektroniczne** dodaj dostawcę konfiguracji. Użyj nazwy firmy jako nazwy dostawcy. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Wybierz właśnie utworzonego dostawcę konfiguracji, a następnie wybierz opcję **Ustaw aktywny**.
4. Wybierz dostawcę konfiguracji **Microsoft**, a następnie **Repozytoria**.
5. W polu **Typ** wybierz **Globalne**.
6. Kliknij przycisk **Otwórz**.
7. Przejdź do **Modelu danych podatkowych**, rozwiń drzewo plików, a następnie wybierz pozycję **Konfiguracja podatków**.
8. Wybierz najnowszą wersję, a następnie **importuj**.
9. Wróć do **obszaru roboczego Funkcje globalizacji (Podgląd)**, wybierz opcję **Funkcje**, wybierz kafelek **Obliczania podatku**, a następnie wybierz opcję **Dodaj**.
10. Umożliwia wybór jednego z następujących typów funkcji:

    - **Nowa funkcja** — umożliwia tworzenie konfiguracji funkcji o pustej zawartości.
    - **Na podstawie istniejącej funkcji** - należy utworzyć funkcję z istniejącej funkcji i skopiować zawartość z istniejącej konfiguracji funkcji.

11. Wprowadź nazwę i opis nowej funkcji, a następnie wybierz **Utwórz funkcje**.

    Po utworzeniu tej funkcji automatycznie tworzona jest wersja robocza tej funkcji.

12. Wybierz wersję roboczą funkcji, a następnie **Edytuj**. Strona **Ustawień obliczania podatku** jest wypełniona.
13. Wybierz **Wersja konfiguracji**. W kroku 8 powinna zostać zaimportowana wersja konfiguracji.

    Firma Microsoft dostarcza domyślną konfigurację podatku dla dodatku do obliczania podatku. Ta konfiguracja pokrywa większość wymagań zachowania w zakresie obliczania podatku. Zostanie on zaktualizowany na podstawie informacji zwrotnej z rynku. Jeśli musisz rozszerzyć konfigurację, aby spełnić określone wymagania, zobacz temat [Jak utworzyć rozszerzenie w usłudze podatków](./tax-service-add-data-fields-tax-integration-by-extension.md), aby uzyskać informacje dotyczące generowania i wybierania własnej konfiguracji podatków.

    Po wybraniu **Wersji konfiguracji** pojawi się kilka dodatkowych kart:

    - **Kody podatku** — ta karta jest obowiązkowa. Służy do obsługi danych master dla kodów podatków. Po włączeniu bieżącej wersji ustawień funkcji podatków w firmie wszystkie kody podatków utworzone na tej karcie są automatycznie synchronizowane z ustawieniami finansów.
    - **Obowiązujące kody podatkowe** — ta karta jest obowiązkowa. Służy do definiowania macierzy, która określa kod podatku, grupę podatków i grupę podatków dla towaru. Określony kod podatku jest używany do obliczania kwoty podatku. Wartości pól **Kod podatku**, **Grupa podatków** i **Grupa podatków** dla pozycji są zwracane do Finance.
    - **Stosowanie numeru rejestracyjnego podatków klienta** — ta karta jest opcjonalna. Jeśli dla jednego odbiorcy istnieje wiele numerów rejestracji podatkowej, obliczanie podatku może automatycznie ustalić poprawny numer rejestracji podatkowej. W macierzy na tej karcie należy zdefiniować reguły używane do określania. W przeciwnym razie w Finance i Supply Chain Management będzie nadal stosować domyślny numer rejestracji podatkowej w dokumentach podlegających opodatkowaniu dla transakcji sprzedaży.
    - **Stosowanie numeru rejestracyjnego podatków dostawcy** — ta karta jest opcjonalna. Jeśli dla jednego dostawcy istnieje wiele numerów rejestracji podatkowej, obliczanie podatku może automatycznie ustalić poprawny numer rejestracji podatkowej. W macierzy na tej karcie należy zdefiniować reguły używane do określania. W przeciwnym razie w Finance i Supply Chain Management będzie nadal stosować domyślny numer rejestracji podatkowej w dokumentach podlegających opodatkowaniu dla transakcji zakupu.
    - **Zastosowanie kodu listy** — ta karta jest opcjonalna. Dzięki bardziej elastycznym i konfigurowalnym regułom można automatycznie określić wartość pola **Kod listy**. W macierzy na tej karcie można zdefiniować reguły używane do określania. W przeciwnym razie w Finance i Supply Chain Management będzie nadal stosować domyślny kod w dokumentach podlegających opodatkowaniu.

14. Na karcie **Kody podatków** wybierz opcję **Dodaj**, a następnie wprowadź kod i opis podatku.
15. Wybierz **Składnik podatku**. Składnik podatku to grupa metod, które zostały zdefiniowane w poprzedniej wersji wybranej konfiguracji podatku. Dostępne są następujące arkusze programu Excel:

    - Kwota netto 
    - Według kwoty brutto
    - Według ilości
    - Według marży
    - Podatek od podatku

16. Wybierz opcję **Zapisz**. Na podstawie wybranego składnika podatku staje się dostępnych więcej pól.
17. Aby określić charakter kodu podatku, należy użyć następujących opcji:

    - Czy podlega zwolnieniu
    - Czy użyć podatku
    - Czy Jest opłatą zwrotną
    - Wyklucz z obliczania kwoty bazowej

    W przypadku scenariusza podatku używanego należy skonfigurować jeden kod podatku z dodatnią stawką podatku i oznaczyć go jako **Podatek Jest używany**.

    W przypadku scenariusza opłaty zwrotnej należy skonfigurować dwa kody podatków, z których jeden ma dodatnią stawkę podatku, a drugi z ujemną stawką podatku, ale z taką samą wartością stawki. Oznacz kod podatku ujemnego jako **Jest opłata zwrotna**. Aby uzyskać więcej informacji o rozwiązaniu opłaty zwrotnej w finansach, zobacz temat [Mechanizm opłaty zwrotnej dla schematu podatku VAT/GST](emea-reverse-charge.md).
    
    W przypadku niektórych typów podatków, które powinny być wykluczone z obliczania kwoty podstawy podatku dla transakcji cenowych, np. cła niestandardowe w niektórych krajach, zaznacz pole wyboru **Wyklucz z obliczania kwoty bazowej**.

    Obsługa stawek podatku i limitów kwoty podatku dla tego kodu podatku.

18. Powtarzaj kroki 14 do 17, aby dodać wszystkie wymagane kody przyczyny.
19. Na karcie **Możliwości stosowania kodów podatków** zaznacz kolumny wymagane do ustalenia poprawnego kodu podatku, a następnie wybierz opcję **Dodaj**.
20. Wprowadź lub wybierz wartości dla każdej kolumny. Wartości pól **Kod podatku**, **Grupa podatków** i **Grupa podatków** dla pozycji są zwracane do Finance.
21. Powtórz kroki od 19 do 20, aby skonfigurować możliwości stosowania numerów rejestracji podatkowej odbiorcy, numerów rejestracji podatkowej dostawcy i kodów list.
22. Wybierz przycisk **Zapisz** i zamknij stronę.
23. Wybierz **Zmień status** \> **Zakończone**. Gdy stan zostanie zmieniony na **Ukończono**, nie będzie można już edytować wersji.
24. Wybierz **Zmień status** \> **Opublikuj**. Ta wersja ustawień funkcji podatków będzie wypychana do repozytorium globalnego i będzie widoczna dla każdej firmy w finansach.

## <a name="dynamics-365-setup"></a>Ustawienia usługi Dynamics 365

Po zakończeniu konfigurowania z rcs, zgodnie z opisem w poprzedniej sekcji, pojawi się opublikowana wersja funkcji podatkowej. Aby skonfigurować obliczanie podatku w środowisku Finance, należy wykonać następujące kroki.

Konfigurację w tej sekcji konfiguruje firma. Należy je skonfigurować dla każdej firmy, dla której ma być włączone obliczanie podatku w aplikacji Finanse.

1. W oknie Finanse przejdź do **Podatek** \> **Ustawienia** \> **Konfiguracja podatku** \> **Obliczanie podatku (wersja zapoznawcza)**.
2. Na karcie **Ogólne** ustaw następujące pola:

    - **Włącz obliczanie podatku** — to pole wyboru należy zaznaczyć, aby włączyć obliczanie podatku dla firmy. Jeśli nie włączono dla bieżącej firmy, firma będzie nadal używać istniejącego aparatu podatków do ustalania i obliczania podatku.
    - **Ustawienia funkcji** – wybierz opublikowaną konfigurację i wersję funkcji podatkowej dla firmy. Aby uzyskać więcej informacji dotyczących sposobu skonfigurowania i ukończenia opublikowanej funkcji podatkowej, zobacz poprzednią sekcję tego tematu.
    - **Proces biznesowy** — wybierz procesy biznesowe, które mają być włączane.
    - **Włącz korektę kodu podatku** – Ustaw tę opcję na wartość **Tak**, aby włączyć korekty kodu podatku na stronie podatku.

3. Na karcie **Obliczania** zdefiniuj oczekiwaną regułę zaokrąglania dla firmy.
4. Na karcie **Obsługa błędów** zdefiniuj oczekiwaną metodę obsługi błędów dla firmy. Dla każdego kodu wynikowego dostępne są trzy opcje:

    - Nr
    - Ostrzeżenie
    - Wadliwe

5. Zapisz konfigurację.
6. Powtórz kroki od 1 do 5 dla każdej dodatkowej firmy.

## <a name="transaction-processing"></a>Przetwarzanie transakcji

Po zakończeniu wszystkich procedur konfiguracji można użyć obliczania podatku w celu ustalenia i obliczenia podatku w Finance. Kroki przetwarzania transakcji pozostają takie same. W wersji finansów 10.0.18 są obsługiwane następujące transakcje:

- Proces sprzedaży

    - Oferta sprzedaży
    - Zamówienie sprzedaży
    - Potwierdzenie
    - Lista pobrania
    - Dokument dostawy
    - Faktura sprzedaży
    - Faktura kredytowa
    - Zwróć zamówienie
    - Opłata w nagłówku
    - Opłata z wiersza

- Proces zakupu

    - Zamówienie zakupu
    - Potwierdzenie
    - Lista przychodu
    - Dokument przyjęcia produktów
    - Faktura zakupu
    - Opłata w nagłówku
    - Opłata z wiersza
    - Faktura kredytowa
    - Zwróć zamówienie
    - Zapotrzebowanie na zakup
    - Stan wiersza zapotrzebowania na zakup
    - Zapytanie ofertowe
    - Opłata od nagłówka zapytania ofertowego
    - Opłata od nagłówka zapytania ofertowego

- Proces zapasów

    - Przeniesienie zamówienia - wysyłka
    - Zamówienie przeniesienia - przyjęcie
