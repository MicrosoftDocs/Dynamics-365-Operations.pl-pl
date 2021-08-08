---
title: Raportowanie JPK-V7M
description: W tym temacie wyjaśniono, jak uruchomić deklarację VAT z rejestrami (znanymi również jako JPK-V7M, VDEK) w Polsce.
author: liza-golub
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: elgolu
ms.openlocfilehash: cfa8c59d106e923f9d015531c02cde0dc4905296
ms.sourcegitcommit: f2dfec2f4c427e37a574e6acdfaaf150bc92ebb6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2021
ms.locfileid: "6661079"
---
# <a name="jpk-v7m-reporting"></a>Raportowanie JPK-V7M

[!include [banner](../includes/banner.md)]

Proces raportowania JPK-V7M jest wstępnie zdefiniowany przez jednostki danych, które zostały dostarczone w pakiecie PL JPK_V7M EM setup.zip. Na poniższej ilustracji przedstawiono przegląd procesu.

![Przepływ procesu raportowania JPK_V7M](media/vdek-em-processing.jpg)

Pakiet PL JPK_V7M EM setup.zip zawiera ustawienia przetwarzania JPK-V7M, które obsługują proces raportowania JPK-V7M. Ta konfiguracja składa się z następujących kroków:

- **Tworzyć:** utworzenie wiadomości elektronicznej do raportowania JPK-V7M.
- **Wygeneruj plik:** generowanie pliku XML w formacie JPK-V7M.
- **Podgląd w programie Excel:** generowanie raportu JPK-V7M w formacie programu Microsoft Excel do podglądu.
- **Zmień status:** zmiana stanu wiadomości elektronicznej.

## <a name="initial-assumptions-for-the-jpk-v7m-report"></a>Wstępne założenia dotyczące raportu JPK-V7M

Implementacja raportu JPK-V7M bazuje na tych samych kodach raportowania podatku, które zostały użyte w raporcie JPK_VAT. Aby uzyskać więcej informacji, zobacz temat [Wygeneruj ewidencję zakupów i sprzedaży VAT JPK](emea-pol-standard-audit-file-saf.md#generate-a-saf-vat-sales-and-purchase-register).

W poniższej tabeli przedstawiono kody raportowania podatku używane w raporcie JPK_VAT i ich mapowanie z elementami **K_\*** raportu JPK-V7M.

| Nazwa elementu     | Opis elementu | Kody raportowania podatku |
|------------------|---------------------|---------------------------|
| K_10             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, zwolnionych od podatku. | 10302, 10402, 10502, 10602 |
| K_11             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług poza terytorium Polski. | 10101, 10102, 10104, 10105, 10201, 10204 |
| K_12             | Wysokość podstawy opodatkowania wynikająca ze świadczenia usług, o których mowa w art. 100 ust. 1 pkt 4 ustawy o VAT. | 10201, 10204 |
| K_13             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 0%. | 10601, 10604, 10701, 10702, 10704, 10705 |
| K_14             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów, o której mowa w art. 129 ustawy o VAT. | 10701, 10702, 10704, 10705 |
| K_15             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 5%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT. | 10501, 10504 |
| K_16             | Wysokość podatku należnego wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 5%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT. | 10503, 10506 |
| K_17             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 7% lub 8%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT. | 10401, 10404 |
| K_18             | Wysokość podatku należnego wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 7% lub 8%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT. | 10403, 10406 |
| K_19             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 22% lub 23%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT. | 10301, 10304 |
| K_20             | Wysokość podatku należnego wynikająca z dostawy towarów oraz świadczenia usług na terytorium Polski, opodatkowanych stawką 22% lub 23%, z uwzględnieniem korekty dokonanej zgodnie z art. 89a ust. 1 i 4 ustawy o VAT. | 10303, 10306 |
| K_21             | Wysokość podstawy opodatkowania wynikająca z wewnątrzwspólnotowej dostawy towarów, o której mowa w art. 13 ust. 1 i 3 ustawy o VAT. | 10807 |
| K_22             | Wysokość podstawy opodatkowania wynikająca z eksportu towarów. | 10901, 10905 |
| K_23             | Wysokość podstawy opodatkowania wynikająca z wewnątrzwspólnotowego nabycia towarów. | 10810, 10811 (zmiana zwrotna) |
| K_24             | Wysokość podatku należnego wynikająca z wewnątrzwspólnotowego nabycia towarów. | 10812 |
| K_25             | Wysokość podstawy opodatkowania wynikająca z importu towarów rozliczanego zgodnie z art. 33a ustawy, potwierdzona zgłoszeniem celnym lub deklaracją importową, o której mowa w art. 33b ustawy o VAT. | 111010 |
| K_26             | Wysokość podatku należnego wynikająca z importu towarów rozliczanego zgodnie z art. 33a ustawy, potwierdzona zgłoszeniem celnym lub deklaracją importową, o której mowa w art. 33b ustawy o VAT. | 11012 |
| K_27             | Podstawa opodatkowania wynikająca z importu usług podlegających art. 28b ustawy o VAT. Usługi zakupione od podatników VAT są wyłączone. | 11110, 11117 (zmiana zwrotna) |
| K_28             | Wartość podatku należnego wynikającego z importu usług podlegających art. 28b ustawy o VAT. Usługi zakupione od podatników VAT są wyłączone. | 11112 |
| K_29             | Wysokość podstawy opodatkowania wynikająca z importu usług nabywanych od podatników podatku od wartości dodanej, do których stosuje się art. 28b ustawy o VAT. | 11210, 11119 (zmiana zwrotna) |
| K_30             | Wysokość podatku należnego wynikająca z importu usług nabywanych od podatników podatku od wartości dodanej, do których stosuje się art. 28b ustawy o VAT. | 11212 |
| K_31             | Wysokość podstawy opodatkowania wynikająca z dostawy towarów, dla których podatnikiem jest nabywca zgodnie z art. 17 ust. 1 pkt 5 ustawy o VAT. | Brak wartości domyślnej |
| K_32             | Wysokość podatku należnego wynikająca z dostawy towarów, dla których podatnikiem jest nabywca zgodnie z art. 17 ust. 1 pkt 5 ustawy o VAT. | Brak wartości domyślnej |
| K_33             | Wysokość podatku należnego od towarów objętych spisem z natury, o którym mowa w art. 14 ust. 5 ustawy o VAT. | Brak wartości domyślnej |
| K_34             | Wysokość zwrotu odliczonej lub zwróconej kwoty wydanej na zakup kas rejestrujących, o którym mowa w art. 111 ust. 6 ustawy o VAT. | Brak wartości domyślnej |
| K_35             | Wysokość podatku należnego od wewnątrzwspólnotowego nabycia środków transportu, wykazana w wysokości podatku należnego z tytułu wewnątrzwspólnotowego nabycia towarów, podlegająca wpłacie w terminie, o którym mowa w art. 103 ust. 3, w związku z ust. 4 ustawy o VAT. | Brak wartości domyślnej |
| K_36             | Wysokość podatku od wewnątrzwspólnotowego nabycia towarów, o których mowa w art. 103 ust. 5aa ustawy, podlegająca wpłacie w terminie, o którym mowa w art. 103 ust. 5a i 5b ustawy o VAT. | Brak wartości domyślnej |
| K_40             | Wartość netto wynikająca z nabycia towarów i usług zaliczanych u podatnika do środków trwałych. | 20107, 20115 |
| K_41             | Wysokość podatku naliczonego przysługującego do odliczenia z podstaw określonych w art. 86 ust. 2 ustawy o VAT, na warunkach określonych w ustawie o VAT wynikająca z nabycia towarów i usług zaliczanych u podatnika do środków trwałych. | 20109 |
| K_42             | Wartość netto wynikająca z nabycia pozostałych towarów i usług. | 20207, 20215 |
| K_43             | Wysokość podatku naliczonego przysługującego do odliczenia z podstaw określonych w art. 86 ust. 2 ustawy o VAT, na warunkach określonych w ustawie o VAT wynikająca z nabycia pozostałych towarów i usług. | 20209 |
| K_44             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o których mowa w art. 90a–90c oraz art. 91 ustawy o VAT, z tytułu nabycia towarów i usług zaliczanych u podatnika do środków trwałych. | 20116 |
| K_45             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o których mowa w art. 90a–90c oraz art. 91 ustawy o VAT, z tytułu nabycia pozostałych towarów i usług. | 20216 |
| K_46             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o której mowa w art. 89b ust. 1 ustawy o VAT. | <p>30101, 30102</p><p>**Uwaga:** w scenariuszu „zaległości” może zostać pobrana kwota z **K_43** lub **K_41**.</p> |
| K_47             | Wysokość podatku naliczonego wynikająca z korekt podatku naliczonego, o której mowa w art. 89b ust. 4 ustawy o VAT. | <p>30201, 30202</p><p>**Uwaga:** w scenariuszu „zaległości” może zostać pobrana kwota z **K_43** lub **K_41**.</p> |

## <a name="create-an-electronic-message-for-jpk-v7m-reporting"></a>Tworzenie wiadomości elektronicznej raportowania JPK-V7M

1. Przejdź do menu **Podatek** > **Zapytania i raporty** > **Wiadomości elektroniczne** > **Wiadomości elektroniczne**.
2. Wybierz **JPK-V7M**, a następnie na skróconej karcie **Wiadomości** wybierz opcję **Nowy**.
3. W oknie dialogowym **Uruchom przetwarzanie** kliknij **OK**.

    ![Okno dialogowe Uruchamianie przetwarzania](media/create-em.jpg)

4. Zostanie utworzona nowa wiadomość elektroniczna. Wprowadź opis i określ datę początkową i końcową okresu, za który chcesz wygenerować raport JPK-V7M.
5. Na skróconej karcie **Dodatkowe pola wiadomości** określ dodatkowe wartości wymagane w części deklaracji raportu V7M.

    ![Skrócona karta Dodatkowe pola wiadomości.](media/message-additional-fields.jpg)

6. W dodatkowym polu **CelZlozenia** określ, czy przesyłany raport jest złożeniem deklaracji czy korektą. Dwie wartości są dozwolone:

    - **1** — to złożenie jest pierwszym złożeniem deklaracji za podany okres. Ta wartość jest wartością domyślną.
    - **2** — to złożenie jest poprawionym złożeniem deklaracji za podany okres.

Można także określić wartości ręczne dla następujących dodatkowych pól, które są powiązane z elementami deklaracji.

| Imię i nazwisko     | Znacznik deklaracji | Opis (EN) | Opis (PL) |
|----------|------------------------|------------------|------------------|
| P_39     | P_39 | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Wysokość nadwyżki podatku naliczonego nad należnym z poprzedniej deklaracji. | Wysokość nadwyżki podatku naliczonego nad należnym z poprzedniej deklaracji |
| P_49     | P_49 | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym pomniejszająca wysokość podatku należnego. Kwota wykazana w **P_49** nie może być większa niż **P_38** – **P_48**. Jeśli **P_38** – **P_48** jest mniejsze lub równe 0 (zero), należy wykazać **0**. | Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym pomniejszająca wysokość podatku należnego |
| P_50     | P_50 | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Wysokość podatku objęta zaniechaniem poboru. Wartość **P_50** nie może być większa niż **P_38** – **P_48** – **P_49**. Jeśli **P_38** – **P_48** – **P_49** jest mniejsze lub równe zero (0) lub większe lub równe **P_50**, należy wykazać **0**. | Wysokość podatku objęta zaniechaniem poboru |
| P_52     | P_52 | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie i zwracana w danym okresie rozliczeniowym. Ewentualnie kwota wydana na zakup kas rejestrujących, która zwiększa kwotę podatku naliczonego do przeniesienia na następny okres rozliczeniowy. | Kwota wydana na zakup kas rejestrujących, do odliczenia w danym okresie rozliczeniowym przysługująca do zwrotu w danym okresie rozliczeniowym lub powiększająca wysokość podatku naliczonego do przeniesienia na następny okres rozliczeniowy |
| P_54     | P_54 | Kwota nadwyżki naliczonego podatku, która musi zostać zwrócona na konto wskazane przez podatnika. | Wysokość nadwyżki podatku naliczonego nad należnym do zwrotu na rachunek wskazany przez podatnika |
| P_54_Powód | P_55, P_56, P_57, P_58, w zależności od wyboru użytkownika | Zwrot na konto bankowe, o którym mowa w art. 87, ust. 6a (**P_55**), 6 (**P_56**), 2 (**P_57**), lub 5a (**P_58**) ustawy o podatku VAT. | Zwrot na rachunek VAT, o którym mowa w art. 87 ust. 6a (P_55) lub 6 (P_56) lub 2 (P_57) lub 5a (P_58) ustawy |
| P_60     | P_60 | Nieujemna liczba całkowita, która ma maksymalnie 14 cyfr. Zaliczenie zwrotu podatku na poczet przyszłych zobowiązań podatkowych. | Wysokość zwrotu do zaliczenia na poczet przyszłych zobowiązań podatkowych |
| P_61     | P_61 | Ciąg (1..240), który musi zostać użyty, jeśli użyte jest **P_60**. Rodzaj przyszłego zobowiązania podatkowego. | Rodzaj przyszłego zobowiązania podatkowego |
| P_ORDZU  | P_ORDZU | Ciąg (1.. 240). Uzasadnienie przyczyn złożenia korekty zwrotu VAT. | Uzasadnienie przyczyn złożenia korekty |

Dodatkowe pole **P_54_Powód** jest dostępne od wersji 98.194 konfiguracji ER **JPK-V7M XML format (PL)** i wersji 98.194.50 konfiguracji raportowania elektronicznego (ER) **JPK-V7M Excel format (PL)**. Może zostać zaimportowane przy użyciu pliku **PL JPK_V7M EM setup v.5 KB4614816.zip** (wersja 5 lub nowsza pakietu encji danych zawierającego wstępnie zdefiniowaną konfiguracją elektronicznej wymiany danych).

## <a name="generate-the-jpk-v7m-report-in-excel-format-for-preview"></a>Wygeneruj raport JPK-V7M w formacie Excel do podglądu

Gdy wszystkie dane są gotowe w systemie, wykonaj następujące kroki, aby wygenerować raport JPK-V7M w formacie programu Excel.

1. Na stronie **Wiadomości elektroniczne** na skróconej karcie **Komunikaty** zaznacz **Generuj raport**.
2. W oknie dialogowym **Uruchamianie przetwarzania** w polu **Akcja** wybierz opcję **Podgląd w programie Excel**.
3. Aby uruchomić generowanie raportu w partii, należy określić parametry na skróconej karcie **Uruchamianie w tle**. Po wygenerowaniu raportu jest on dołączany do wiadomości elektronicznej jako plik.
4. Kliknij przycisk **OK**.

    ![Użycie okna dialogowego Uruchom przetwarzanie do wygenerowania raportu JPK-V7M w formacie Excel](media/generate-vdek.jpg)

5. Aby obejrzeć plik, wybierz wiadomość elektroniczną, po czym naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony.
6. Na stronie **Załączniki wiadomości** wybierz załącznik, a następnie, w okienku akcji, wybierz **Otwórz**.

## <a name="generate-an-xml-file-in-jpk-v7m-format"></a>Generowanie pliku XML w formacie JPK-V7M

Gdy wszystkie dane są gotowe w systemie, wykonaj poniższe czynności, aby wygenerować plik XML w formacie JPK-V7M.

1. Na stronie **Wiadomości elektroniczne** na skróconej karcie **Komunikaty** zaznacz **Generuj raport**.
2. Aby uruchomić generowanie raportu w partii, w oknie dialogowym **Uruchamianie przetwarzania** określ parametry na skróconej karcie **Uruchom w tle**.
3. Kliknij przycisk **OK**.

    ![Użycie okna dialogowego Uruchom przetwarzanie do wygenerowania pliku XML w formacie JPK-V7M](media/generate-xml-vdek.jpg)

Po naciśnięciu **OK** w oknie dialogowym powinien pojawić się następujący tekst oświadczenia:

- **Angielski:** "When you generate the VAT declaration you confirm information in the report is true and complete. Your consent will be recorded in the report. Incomplete payment or non-payment of VAT due to the Tax Authority, this declaration is the basis for the issuance of a writ of execution in accordance with the provisions of the enforcement proceedings in the administration. A false or incomplete declaration may result in prosecution in accordance with regulations of fiscal penal code."
- **Polski:** „Wygenerowanie deklaracji VAT oznacza potwierdzenie, że informacje w raporcie są prawdziwe i kompletne. Twoja zgoda zostanie odnotowana w raporcie. W przypadku niewpłacenia w obowiązującym terminie podatku podlegającego wpłacie do urzędu skarbowego lub wpłacenia go w niepełnej wysokości niniejsza deklaracja stanowi podstawę do wystawienia tytułu wykonawczego zgodnie z przepisami o postępowaniu egzekucyjnym w administracji. Za podanie nieprawdy lub zatajenie prawdy i przez to narażenie podatku na uszczuplenie grozi odpowiedzialność przewidziana w przepisach Kodeksu karnego skarbowego”.

Naciskając **OK** na stronie oświadczenia, wyrażasz zgodę na oświadczenie. JPK_VDEK zostanie wygenerowana tylko wtedy, gdy użytkownik wyrazi zgodę na oświadzcenie.

Dziennik akcji jest związany z informacjami dziennika wiadomości elektronicznych dotyczącymi użytkownika, który wygenerował JPK_VDEK i wykonał inne akcje z wiadomością elektroniczną.

Po wygenerowaniu pliku XML raportu JPK_V7M jest on dołączany do wiadomości elektronicznej. Aby obejrzeć plik, wybierz wiadomość elektroniczną, po czym naciśnij przycisk **Załączniki** (symbol spinacza) w prawym górnym rogu strony. Na stronie **Załączniki wiadomości** wybierz załącznik, a następnie, w okienku akcji, wybierz **Otwórz**.

## <a name="change-the-status-of-the-electronic-message"></a>Zmienianie stanu wiadomości elektronicznej

Po zakończeniu pracy z raportem można zmienić stan na **Zgłoszone JPK_VDEK** (**Reported JPK-V7M**). Wiadomości elektronicznej w tym stanie nie można usunąć. W razie konieczności można zmienić stan z powrotem na **Wygenerowane JPK_VDEK**.

Aby zmienić stan wiadomości elektronicznej, na skróconej karcie **Wiadomości** wybierz opcję **Aktualizuj stan** \> **Nowy stan**.

## <a name="generate-the-jpk-v7m-report-for-part-of-a-month"></a>Generowanie raportu JPK-V7M za część miesiąca

Możesz przygotować raport JPK-V7M dla okresów krótszych niż pełny miesiąc. Na stronie **Wiadomości elektroniczne** (**Podatek** > **Informacje i raporty** > **Wiadomości elektroniczne** > **Wiadomości elektroniczne**) użyj pól **Od dnia** i **Do dnia**, aby zdefiniować interwał dat, dla którego ma zostać wygenerowany raport JPK-V7M. Te daty muszą należeć do tego samego miesiąca kalendarzowego.

W przypadku generowania raportu JPK-V7M w formacie XML za okres krótszy niż pełny miesiąc pojawi się ostrzeżenie, że raport jest generowany za mniej niż pełny miesiąc i nie będzie mógł zostać przesłany do urzędu. Raport będzie zawierał także następujące informacje wskazujące, że nie jest za pełny miesiąc:

- Tag **\<Miesiac\>** będzie zawierać informacje o interwale dat, za który jest generowany raport.
- Tag **\<P_\*\>** części **Deklaracja** raportu zawiera obliczone wartości reprezentujące agregację kwot z części **SprzedazWiersz** i **ZakupWiersz** raportu. Wartości w tym tagu zostaną zaokrąglone do dwucyfrowej wartości dziesiętnej, ale nie wartości całkowitej.
