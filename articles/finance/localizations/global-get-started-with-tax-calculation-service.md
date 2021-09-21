---
title: Rozpoczynanie pracy z obliczaniem podatku
description: W tym temacie wyjaśniono, jak skonfigurować obliczanie podatku.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b180a8cee1c5b7e9dda837915e6fdf94af30d06a
ms.sourcegitcommit: 8246ba3872a1f3eaa18c8bb1ba86d3c2142a6e10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2021
ms.locfileid: "7465084"
---
# <a name="get-started-with-tax-calculation"></a>Rozpoczynanie pracy z obliczaniem podatku

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ten temat zawiera informacje dotyczące sposobu rozpoczęcia pracy z obliczaniem podatku. Przeprowadzi użytkownika przez etapy konfiguracji Microsoft Dynamics Lifecycle Services (usługi LCS), Regulatory Configuration Services (RCS) Dynamics 365 Finance i Dynamics 365 Supply Chain Management. Następnie przegląda wspólny proces korzystania z funkcji obliczania podatków w transakcjach zarządzania Finance i Supply Chain Management.

Ta konfiguracja składa się z następujących czterech kroków:

1. W LCS zainstaluj dodatek do obliczania podatku.
2. W RCS należy skonfigurować funkcję obliczania podatku. Te dane konfiguracyjne nie są specyficzne dla pojedynczej firmy. Można je udostępnić innym podmiotom prawnym w zarządzaniu Finance i Supply Chain Management.
3. W Finance i Supply Chain Management dostaw skonfiguruj parametry obliczania podatku według firmy.
4. W programie Finance and Supply Chain Management utwórz transakcje, takie jak zamówienia sprzedaży, i użyj funkcji Obliczanie podatku do określania i obliczania podatków.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie muszą być spełnione wymagania wstępne dotyczące poszczególnych typów środowiska:

### <a name="for-a-production-environment"></a>W przypadku środowiska produkcyjnego

W przypadku środowiska produkcyjnego muszą być spełnione następujące wymagania wstępne:

- Musisz mieć dostęp do swojego konta usługi LCS i mieć wdrożony projekt usługi LCS ze środowiskiem warstwy 2 (lub wyższej), w którym jest uruchomiona wersja Dynamics 365 10.0.21 lub nowsza.
- Musisz utworzyć środowisko RCS dla swojej organizacji i mieć dostęp do swojego konta. Aby uzyskać więcej informacji dotyczących sposobu tworzenia środowiska RCS, zobacz temat [Omówienie usługi Regulatory Configuration Service](rcs-overview.md).
- Następujące funkcje muszą być włączone w obszarze roboczym **Zarządzanie funkcjami** w wdrożonym środowisku Finance lub Supply Chain Management, zależnie od indywidualnych potrzeb:

    - Usługa obliczania podatku
    - Obsługa wielu numerów rejestracji VAT
    - Podatek w zleceniu przeniesienia

- Następujące funkcje muszą być włączone w obszarze roboczym **Zarządzanie funkcjami** w wdrożonym środowisku RCS.

    - Funkcje globalizacji

### <a name="for-a-test-environment-public-preview"></a>W przypadku środowiska testowego (publiczna wersja zapoznawcza)

W przypadku środowiska testowego muszą być spełnione następujące wymagania wstępne:

- Musisz mieć dostęp do swojego konta usługi LCS i mieć wdrożony projekt usługi LCS ze środowiskiem warstwy 2 (lub wyższej), w którym jest uruchomiona wersja Dynamics 365 10.0.21 lub nowsza wersja.
- Musisz utworzyć środowisko RCS dla swojej organizacji i mieć dostęp do swojego konta. Aby uzyskać więcej informacji dotyczących sposobu tworzenia środowiska RCS, zobacz temat [Omówienie usługi Regulatory Configuration Service](rcs-overview.md).
- Musisz skontaktować się z firmą Microsoft, wysyłając e-mail na adres <taxcalc@microsoft.com>, w sprawie włączenia lotowania w wdrożonym środowisku Finance lub Supply Chain Management.
- Następujące funkcje muszą być włączone w obszarze roboczym **Zarządzanie funkcjami** w wdrożonym środowisku Finance lub Supply Chain Management, zależnie od indywidualnych potrzeb:

    - Usługa obliczania podatku
    - Obsługa wielu numerów rejestracji VAT
    - Podatek w zleceniu przeniesienia

- Następujące funkcje muszą być włączone w obszarze roboczym **Zarządzanie funkcjami** w wdrożonym środowisku RCS.

    - Funkcje globalizacji

## <a name="set-up-tax-calculation-in-lcs"></a>Skonfiguruj obliczanie podatku w LCS

1. Zaloguj się w rozwiązaniu [LCS](https://lcs.dynamics.com)
2. Ukończ konfigurację integracji Microsoft Power Platform. Aby uzyskać więcej informacji, zobacz [Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Wybierz jedno ze wdrożonych środowisk, a następnie wybierz opcję **Zainstaluj nowy dodatek**.
4. Wybierz opcję **Obliczanie podatku**.
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
8. Wybierz poprawną wersję konfiguracji podatku zależnie od wersji modułu Finance, a następnie wybierz pozycję **Importuj**.

    | Wersja wydania | Konfiguracja podatku                       |
    | --------------- | --------------------------------------- |
    | 10.0.18         | Konfiguracja podatku — Europa 30.12.82     |
    | 10.0.19         | Konfiguracja obliczania podatku 36.38.193 |
    | 10.0.20         | Konfiguracja obliczania podatku 40.43.208 |
    | 10.0.21         | Konfiguracja obliczania podatku 40.46.212 |

9. W obszarze roboczym **Funkcje globalizacji**, wybierz opcję **Funkcje**, wybierz kafelek **Obliczania podatku**, a następnie wybierz opcję **Dodaj**.
10. Umożliwia wybór jednego z następujących typów funkcji:

    - **Nowa funkcja** — umożliwia tworzenie konfiguracji funkcji o pustej zawartości.
    - **Na podstawie istniejącej funkcji** - należy utworzyć funkcję z istniejącej funkcji i skopiować zawartość z istniejącej konfiguracji funkcji.

11. Wprowadź nazwę i opis nowej funkcji, a następnie wybierz **Utwórz funkcje**.

    Po utworzeniu tej funkcji automatycznie tworzona jest wersja robocza tej funkcji. Wybierając opcję **Pobierz tę wersję**, możesz zmienić podstawę wersji roboczej na dowolną ukończoną wersję.

12. Wybierz wersję roboczą funkcji, a następnie **Edytuj**. Strona **Ustawień obliczania podatku** jest wypełniona.
13. Wybierz **Wersja konfiguracji**. W kroku 8 powinna zostać zaimportowana wersja konfiguracji.

    Firma Microsoft dostarcza domyślną konfigurację podatku do obliczania podatku. Ta konfiguracja pokrywa większość wymagań zachowania w zakresie obliczania podatku. Zostanie on zaktualizowany na podstawie informacji zwrotnej z rynku. Jeśli musisz rozszerzyć konfigurację, aby spełnić określone wymagania, zobacz temat [Jak utworzyć rozszerzenie w usłudze podatków](./tax-service-add-data-fields-tax-integration-by-extension.md), aby uzyskać informacje dotyczące generowania i wybierania własnej konfiguracji podatków.

14. Po wybraniu pozycji **Wersja konfiguracji** pojawi się kilka dodatkowych kart. Postępuj zgodnie z kolejnością, która jest wyświetlana w tym miejscu, aby dokończyć obowiązkową konfigurację kart.

    **Obowiązkowa konfiguracja**

    - **Kody podatku** — obsługa danych głównych kodów podatku. Po włączeniu bieżącej wersji wszystkie kody podatku utworzone na tej karcie są automatycznie synchronizowane z ustawieniami modułu Finance.
    - **Grupa podatków** — służy do definiowania danych głównych grup podatków i kodów podatku w grupie.
    - **Grupa podatków dla pozycji** — służy do definiowania danych głównych grup podatków dla pozycji i kodów podatku w grupie.

    **Ustawienia opcjonalne**

    - **Stosowanie grupy podatków** — określenie matrycy, która wyznacza grupę podatków. Jeśli żadne reguły możliwości zastosowania w tej matrycy nie są zgodne z dokumentem podlegającym opodatkowaniu z usługi Dynamics 365, w obliczeniach podatku jest używana wartość domyślna w wierszu dokumentów podlegających opodatkowaniu.
    - **Stosowanie grupy podatków dla pozycji** — określenie matrycy, która wyznacza grupę podatków dla pozycji. Jeśli żadne reguły możliwości zastosowania w tej matrycy nie są zgodne z dokumentem podlegającym opodatkowaniu z usługi Dynamics 365, w obliczeniach podatku jest używana wartość domyślna w wierszu dokumentów podlegających opodatkowaniu.
    - **Stosowanie numeru rejestracyjnego podatków klienta** — jeśli dla jednego odbiorcy istnieje wiele numerów rejestracji podatkowej, dodatek Obliczanie podatku może automatycznie ustalić poprawny numer rejestracji podatkowej. W matrycy na tej karcie należy zdefiniować reguły używane do określania. W przeciwnym razie w Finance i Supply Chain Management będzie nadal stosować domyślny numer rejestracji podatkowej w dokumentach podlegających opodatkowaniu dla transakcji sprzedaży.
    - **Stosowanie numeru rejestracyjnego podatków dostawcy** — jeśli dla jednego dostawcy istnieje wiele numerów rejestracji podatkowej, dodatek Obliczanie podatku może automatycznie ustalić poprawny numer rejestracji podatkowej. W matrycy na tej karcie należy zdefiniować reguły używane do określania. W przeciwnym razie w Finance i Supply Chain Management będzie nadal stosować domyślny numer rejestracji podatkowej w dokumentach podlegających opodatkowaniu dla transakcji zakupu.
    - **Zastosowanie kodu listy** — dzięki bardziej elastycznym i konfigurowalnym regułom można automatycznie określić wartość pola **Kod listy**. W matrycy na tej karcie należy zdefiniować reguły używane do określania. W przeciwnym razie w Finance i Supply Chain Management będzie nadal stosować domyślny kod w dokumentach podlegających opodatkowaniu.

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
    - Czy jest podatkiem obrotowym
    - Jest opłatą zwrotną
    - Wyklucz z obliczania kwoty bazowej

    W przypadku scenariusza podatku obrotowego należy skonfigurować jeden kod podatku z dodatnią stawką podatku i oznaczyć go jako **Czy jest podatkiem obrotowym**.

    W przypadku scenariusza opłaty zwrotnej należy skonfigurować dwa kody podatków, z których jeden ma dodatnią stawkę podatku, a drugi z ujemną stawką podatku, ale z taką samą wartością stawki. Oznacz kod podatku ujemnego jako **Jest opłata zwrotna**. Aby uzyskać więcej informacji o rozwiązaniu opłaty zwrotnej w finansach, zobacz temat [Mechanizm opłaty zwrotnej dla schematu podatku VAT/GST](emea-reverse-charge.md).

    W przypadku niektórych typów podatków, które powinny być wykluczone z obliczania kwoty podstawy podatku dla transakcji cenowych (np. cła niestandardowe w niektórych krajach lub regionach), należy zaznaczyć pole wyboru **Wyklucz z obliczania kwoty bazowej**. Aby uzyskać więcej informacji o tym parametrze, zobacz temat [Obliczanie podatku w dodatku do ceny, gdy ceny zawierają podatki jest włączone](global-exclude-from-tax-base-amount-calculation.md).

    Obsługa stawek podatku i limitów kwoty podatku dla tego kodu podatku.

18. Powtarzaj kroki 14 do 17, aby dodać wszystkie wymagane kody przyczyny.
19. Na karcie **Grupa podatków** zaznacz kolumnę **Grupa podatków**, dodaj ją do matrycy jako warunek wejściowy, a następnie dodaj wiersze w celu obsługi danych głównych grupy podatków.

    Oto przykład.

    | Grupa podatków    | Kody podatków           |
    | ------------ | ------------------- |
    | DEU_Domestic | DEU_VAT19; DEU_VAT7 |
    | DEU_EU       | DEU_Exempt          |
    | BEL_Domestic | BEL_VAT21; BEL_VAT6 |
    | BEL_EU       | BEL_Exempt          |

20. Na karcie **Grupa podatków dla pozycji** zaznacz kolumnę **Grupa podatków dla pozycji**, dodaj ją do matrycy jako warunek wejściowy, a następnie dodaj wiersze w celu obsługi danych głównych grupy podatków dla pozycji.

    Oto przykład.

    | Grupa podatków dla pozycji | Kody podatków                                    |
    | -------------- | -------------------------------------------- |
    | Pełny           | DEU_VAT19; BEL_VAT21; DEU_Exempt; BEL_Exempt |
    | Zredukowane        | DEU_VAT7; BEL_VAT6; DEU_Exempt; BEL_Exempt   |

21. Na karcie **Zastosowanie grupy podatków** zaznacz kolumny wymagane do ustalenia poprawnej grupy podatków, a następnie wybierz opcję **Dodaj**. Wprowadź lub wybierz wartości dla każdej kolumny. Pole **Grupa podatków** będzie wynikiem tej matrycy. Jeśli ta karta nie jest skonfigurowana, zostanie użyta grupa podatków z wiersza transakcji.

    Oto przykład.

    | Proces biznesowy | Przysłane z | Wysłać do | Grupa podatków    |
    | ---------------- | --------- | ------- | ------------ |
    | Sprzedaż            | DEU       | DEU     | DEU_Domestic |
    | Sprzedaż            | DEU       | FRA     | DEU_EU       |
    | Sprzedaż            | BEL       | BEL     | BEL_Domestic |
    | Sprzedaż            | BEL       | FRA     | BEL_EU       |

22. Na karcie **Zastosowanie grupy podatków dla pozycji** zaznacz kolumny wymagane do ustalenia poprawnej grupy podatków dla pozycji, a następnie wybierz opcję **Dodaj**. Wprowadź lub wybierz wartości dla każdej kolumny. Pole **Grupa podatków dla pozycji** będzie wynikiem tej matrycy. Jeśli ta karta nie jest skonfigurowana, zostanie użyta grupa podatków dla pozycji z wiersza transakcji.

    Oto przykład.

    | Kod pozycji | Grupa podatków dla pozycji |
    | --------- | -------------- |
    | D0001     | Pełny           |
    | D0003     | Zredukowane        |

    Aby uzyskać więcej informacji na temat określania kodów podatków w obliczaniu podatku, zobacz temat [Logika określania grupy podatków i grupy podatków dla pozycji](global-sales-tax-group-determination.md).

23. Skonfiguruj możliwości stosowania numerów rejestracji podatkowej odbiorcy, numerów rejestracji podatkowej dostawcy i kodów list stosownie do indywidualnych potrzeb.
24. Wybierz przycisk **Zapisz** i zamknij stronę.
25. Wybierz **Zmień status** \> **Zakończone**. Gdy stan zostanie zmieniony na **Ukończono**, nie będzie można już edytować wersji.
26. Wybierz **Zmień status** \> **Opublikuj**. Ta wersja ustawień funkcji podatków będzie wypychana do repozytorium globalnego i będzie widoczna dla każdej firmy w finansach.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Skonfiguruj obliczanie podatku w Dynamics 365

Po zakończeniu konfigurowania w RCS pojawi się opublikowana wersja funkcji podatku. Aby skonfigurować obliczanie podatku w środowisku Finance, należy wykonać następujące kroki.

Konfigurację w tej sekcji konfiguruje firma. Należy je skonfigurować dla każdej firmy, dla której ma być włączone obliczanie podatku w aplikacji Finanse.

1. W module Finance wybierz opcje **Podatek** \> **Ustawienia** \> **Konfiguracja podatku** \> **Parametry obliczania podatku**.
2. Na karcie **Ogólne** ustaw następujące pola:

    - **Włącz usługę obliczanie podatku** — to pole wyboru należy zaznaczyć, aby włączyć obliczanie podatku dla firmy. Jeśli nie włączono dla bieżącej firmy, firma będzie nadal używać istniejącego aparatu podatków do ustalania i obliczania podatku.
    - **Ustawienia funkcji** – wybierz opublikowaną konfigurację i wersję funkcji podatkowej dla firmy. Aby uzyskać więcej informacji dotyczących sposobu skonfigurowania i ukończenia opublikowanej funkcji podatkowej, zobacz poprzednią sekcję tego tematu.
    - **Proces biznesowy** — wybierz procesy biznesowe, które mają być włączane.

3. Na karcie **Obliczania** zdefiniuj oczekiwaną regułę zaokrąglania dla firmy. Aby uzyskać więcej informacji o logice zaokrąglania, zobacz temat [Reguły zaokrąglania obliczania podatku](https://go.microsoft.com/fwlink/?linkid=2166988).
4. Na karcie **Obsługa błędów** zdefiniuj oczekiwaną metodę obsługi błędów dla firmy. Dostępne są trzy opcje:

    - Nr
    - Ostrzeżenie
    - Wadliwe

    W sekcji **Szczegóły** można skonfigurować metodę obsługi błędów w przypadku poszczególnych kodów wyniku. Jeśli niektóre kody wyników nie są synchronizowane z usługą obliczania podatku, można skonfigurować domyślną metodę w sekcji **Ogólne**.

5. Na karcie **Wiele rejestracji podatku VAT** można włączyć oddzielnie działanie deklaracji VAT, listy sprzedaży do UE oraz raportów Intrastat w scenariuszach wielu rejestracji podatku VAT. Aby uzyskać więcej informacji o raportowaniu podatku w przypadku wielu rejestracji VAT, zobacz temat [Raportowanie dla wielu numerów rejestracji podatku VAT](emea-reporting-for-multiple-vat-registrations.md).
6. Zapisz konfigurację i wykonaj te same kroki z każdą dodatkową firmą. Gdy zostanie opublikowana nowa wersja i ma zostać zastosowana, ustaw pole **Konfiguracja funkcji** na karcie **Ogólne** strony **Parametry obliczania podatku** (krok 2).

## <a name="transaction-processing"></a>Przetwarzanie transakcji

Po zakończeniu wszystkich procedur konfiguracji można użyć obliczania podatku w celu ustalenia i obliczenia podatku w Finance. Kroki przetwarzania transakcji pozostają takie same. W wersji finansów 10.0.21 są obsługiwane następujące transakcje:

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
