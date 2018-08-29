---
title: "Konfigurowanie i praca z alertami o oszustwach w biurze obsługi"
description: "W tym temacie wyjaśniono sposób konfigurowania reguł powiadomień dla działu obsługi klienta o potencjalnie fałszywych informacjach przy przetwarzaniu zamówień. Można zdefiniować określone kody używane do automatycznego lub ręcznego wstrzymania podejrzanych zamówień."
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: SalesPostingHistory, MCRHoldCodeTrans, SysOperationTemplateForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 6cca9e5b606f298d000354f6aeb01fbe2c8f2141
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="set-up-and-work-with-call-center-fraud-alerts"></a>Konfigurowanie i praca z alertami o oszustwach w biurze obsługi

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób ustawiania kryteriów i zasad tak, aby wstrzymać potencjalnie fałszywe zamówienia sprzedaży w celu dalszego sprawdzenia. Funkcja wykrywania oszustw służy do określania prawidłowości informacji w zamówieniu sprzedaży. Jeżeli informacje w zamówieniu sprzedaży budzą wątpliwości na podstawie obowiązujących w organizacji kryteriów i zasad dotyczących oszustw, zamówienie można wstrzymać w celu dalszego sprawdzenia. W takim przypadku nie można zwolnić zamówienia do magazynu w celu dalszego przetwarzania do czasu, aż blokada zostanie zdjęta.

> [!NOTE]
> Tej funkcji można używać tylko z przetwarzaniem zamówień sprzedaży dla kanału Biuro obsługi rozwiązania Retail.

## <a name="turning-on-the-fraud-check-feature"></a>Włączanie funkcji wykrywania oszustw

Aby korzystać z funkcji kontroli pod kątem oszustwa, należy ustawić opcję **Włącz kończenie zamówienia** na kanale **Tak**, gdy kanał biura obsługi jest [zdefiniowany](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/set-up-order-processing-options). Jeśli wykonanie zlecenia jest włączone, użytkownicy biura obsługi muszą wybrać **Zakończ** na stronie zamówień sprzedaży dla wszystkich zamówień sprzedaży, które zostały utworzone. Akcja Wykonane powoduje otwarcie strony **Podsumowanie zamówienia sprzedaży**. Gdy użytkownicy wprowadzą wymagane dane płatności na stronie **Podsumowanie zamówienia sprzedaży**, muszą nacisnąć przycisk **Prześlij**, aby sfinalizować zamówienie. Po przesłaniu zamówienia, zostanie uruchomiona funkcja kontroli pod kątem oszustwa,a wszystkie reguły, które są aktywne w systemie, zostaną automatycznie sprawdzone.

Użytkownicy biura obsługi mogą także ręcznie wstrzymywać zamówienia sprzedaży do weryfikacji pod kątem oszustwa, zanim nacisną opcję **Prześlij**. Aby ręcznie wstrzymać zamówienie sprzedaży, na stronie **Podsumowanie zamówienia sprzedaży** wybierz opcję **Wstrzymanie** \> **Ręczne wstrzymanie ze względu na oszustwo**. Następnie zostanie wyświetlony monit o wprowadzenie komentarza wyjaśniającego przyczynę wstrzymania zamówienia. Ten komentarz pojawi się na pulpicie [wstrzymanie zamówień](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/work-with-order-holds), aby dostarczyć kontekst użytkownikom sprawdzającym wstrzymane zamówienia w celu określenia, czy dane zamówienie powinno być zwolnione.

Oprócz skonfigurowania opcji **Włącz kończenie zamówienia** w kanale należy również skonfigurować funkcję wykrywania oszustw w oknie Parametry biura obsługi. Wybierz kolejno opcje **Handel detaliczny** \> **Ustawienia kanału** \> **Ustawienia biura obsługi** \> **Parametry biura obsługi**. Na stronie **Parametry biura obsługi** na karcie **Wstrzymania** w opcji **Wykrywanie oszustw** ustaw wartość **Tak**.

Na kartę **Wstrzymania** należy także zdefiniować [kody wstrzymania](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/work-with-order-holds), które będą stosowane do zamówienia wstrzymanego ręcznie lub automatycznie w celu weryfikacji pod kątem oszustwa. Ustaw kody wstrzymania w polach **Kod ręcznego wstrzymania z powodu oszustwa** i **Kod wstrzymania z powodu oszustwa**. Może być przydatne utworzenie dwóch unikatowych kodów wstrzymania. Dzięki temu użytkownicy pracujący na pulpicie wstrzymań mogą z łatwością odfiltrować i odróżnić automatyczne wstrzymania od ręcznych.

Aby funkcja wykrywania oszustw działała skutecznie, należy także ustawić pole **Minimalna punktacja**. Każde kryterium i reguła wykrywania oszustw zdefiniowane w systemie ma punktację. Gdy zamówienie sprzedaży jest sprawdzane pod kątem dopasowań oszustwa, jeśli jedno lub więcej dopasowań zostanie znalezionych, wyniki są dodawane, aby uzyskać łączną punktację oszustwa. Jeśli łączny wynik punktowy w ocenie oszustwa dla zamówienia przekracza wartość w polu **Minimalna punktacja**, zamówienie zostanie automatycznie wstrzymane. Można opcjonalnie użyć innych powiązanych pól związanych z wynikami na karcie **Wstrzymania**, aby zdefiniować punktację dla adresu e-mail, numeru telefonu, kodu pocztowego i rozszerzonego kodu pocztowego. Jeśli nie określisz wyniku punktowego dla któregokolwiek z tych statycznych kryteriów wykrywania oszustw podczas ich definiowania na stronie **Dane statyczne oszustw**, system będzie je oceniał przy użyciu domyślnych wyników punktowych określonych na karcie **Wstrzymania** na stronie **Parametry biura obsługi**.

Na koniec użyj pola **Typ komentarza do oszustwa**, aby określić typ dokumentu, który ma być używany, gdy użytkownicy wprowadzają komentarze podczas ręcznego wstrzymywania zamówienie w celu weryfikacji pod kątem oszustwa. Najczęściej w tym polu ustawia się wartość **Uwaga**.

## <a name="defining-fraud-criteria-and-rules"></a>Definiowanie kryteriów i reguł wykrywania oszustw

System odwołuje się do dwóch typów kryteriów wykrywania oszustw, aby określić, czy należy wstrzymać zamówienie w celu sprawdzenia, czy nie stanowi oszustwa:

- **Dane statyczne oszustw** używają określonej wartości, takiej jak numer telefonu umieszczony na liście zablokowanych numerów lub adres e-mail oflagowany, ponieważ wiadomo, że był używany w poprzednich oszukańczych transakcjach. Aby skonfigurować dane statyczne oszustw, przejdź do **Sprzedaż detaliczna** \> **Konfiguracja kanału** \> **Ustawienia biura obsługi** \> **Oszustwa** \> **Dane statyczne oszustw**. Na stronie **Fałszywe dane statyczne** można dodać kryteria uznawania za oszustwo ręcznie lub za poprzez import danych. Wyniki zostaną dołączone do fałszywych informacji. Jeżeli funkcja wykrywania oszustw jest włączona, każde wprowadzone zamówienie sprzedaży zostanie porównane z danymi statycznymi. Jeśli dane zostaną znalezione w adresie rozliczeniowym klienta lub adresie dostawy połączonym z nagłówkiem zamówienia albo w adresach dostawy połączonych z którymkolwiek wierszem tego zamówienia sprzedaży, wyniki punktowe wszystkich unikatowych pasujących elementów zostaną zsumowane i porównane z wartością **Minimalna punktacja** w celu określenia, czy zamówienie należy wstrzymać.
- **Reguły oszustw** składają się ze zmiennych zdefiniowanych przez użytkownika oraz warunków zdefiniowanych dla tych zmiennych. Aby utworzyć reguły, przejdź do **Sprzedaż detaliczna** \> **Konfiguracja kanału** \> **Ustawienia centrum obsługi telefonicznej** \> **Oszustwa** \> **Reguły**. Mechanizm reguł wykrywania oszustw umożliwia firmie skonfigurowanie bardziej złożonego zestawu reguł, który może zawierać instrukcje **I** albo **LUB** pozwalające oceniać wiele warunków. Na przykład użytkownik chce, aby wszystkie zamówienia od odbiorców, którzy należą do określonej grupy odbiorców i zamówili określony produkt, zostały wstrzymane w celu sprawdzenia pod kątem oszustw. W takim przypadku warunki sprawdzania poprawności odbiorcy i produktów są definiowane na stronie **Reguły** oraz jest używany warunek I. Zamówienie jest następnie wstrzymywane tylko wtedy, gdy oba warunki są spełnione, a wartości wyniku przypisana do tej reguły oraz wartości wyników wszystkich innych reguł spełnianych przez zamówienie powodują, że łączna punktacja oszustwa dla zamówienia przekracza wartość **Minimalna punktacja** określoną na stronie **Parametry biura obsługi**.

> [!NOTE]
> Ustawienie wielu reguł lub zbyt złożonych reguł wpłynie na wydajność systemu po przesłaniu zamówień sprzedaży. Funkcja wykrywania oszustw nie została zoptymalizowana do obsługi dużej liczby statycznych wpisów danych o oszustwach i wielu aktywnych reguł. Należy pamiętać, że każda reguła jest oceniana, gdy użytkownik biura obsługi naciśnie opcję **Prześlij** podczas wprowadzania zamówienia sprzedaży. Te reguły są oceniane względem nagłówka zamówienia sprzedaży i wszystkich wierszy zamówień. Im więcej zasad i im większa złożoność instrukcji reguły, tym więcej czasu potrzeba na przetwarzanie. Jeżeli w zamówieniu istnieje duża liczba pozycji w wierszach oraz wiele aktywnych reguł i wpisów danych statycznych, automatyczny proces przeglądania i sprawdzania poprawności wszystkich danych oraz obliczania punktacji w ocenie oszustwa może mieć duży wpływ na wydajność. Organizacje korzystające z tej funkcji powinny zawsze przetestować i sprawdzić, czy czas przetwarzania przesyłania zamówień jest akceptowalny, zanim zastosują zmiany w regułach lub statycznych kryteriach uznawania za oszustwa w środowisku produkcyjnym.

## <a name="identifying-orders-that-are-on-hold-for-fraud-review"></a>Identyfikowanie zamówień wstrzymanych w celu weryfikacji pod kątem oszustwa

Kiedy biuro obsługi przesyła zamówienie sprzedaży, jeśli zamówienie pasuje do kryterium lub reguł oszustwa, a wynik przekracza minimum, użytkownicy otrzymują komunikat ostrzegawczy, który stanowi, że zamówienie zostało wstrzymane. Użytkownicy mogą zamknąć tę wiadomość, ponieważ jest ona tylko do celów informacyjnych. Użytkownicy mogą opcjonalnie przekazać tę informację odbiorcy. Działalność powinna określić protokół, który w takiej sytuacji użytkownicy powinni wykonać.

Zamówienie zostanie zapisane, ale z flagą **Nie przetwarzaj**. Ta flaga pozwala zagwarantować, że zamówienie nie może zostać zwolnione do magazynu. W dowolnym momencie użytkownik może wyświetlić ustawienie flagi **Nie przetwarzaj** dla każdego zamówienia sprzedaży figurującego na stronie **Szczegółowy stan**. Tę stronę można otworzyć ze stron **Wszystkie zamówienia sprzedaży** i **Obsługa klienta**. Ponadto system aktualizuje wartość pola **Szczegółowy stan** dla zamówienia do **Wstrzymanie z powodu oszustwa**.

Aby zobaczyć podgląd i zarządzać zamówieniami, które są wstrzymane ze względu na kontrolę pod kątem oszustwa, przejdź do **Sprzedaży detalicznej** \> **Odbiorców** \> **Wstrzymane zamówienia**. Na stronie **Wstrzymania zamówień** wybierz pozycję na liście, a następnie kliknij opcję **Wstrzymanie zamówienia**, aby zobaczyć bardziej szczegółowy widok zawierający m.in. informacje o przyczynie wstrzymania. Na skróconej karcie **Szczegóły oszustwa** można obejrzeć systematyczne kryteria oszustwa, dla których znaleziono pasujące elementy w zamówieniu, oraz zastosowane wyniki. Jeśli zamówienie zostało wstrzymane ręcznie, można przejrzeć wszystkie komentarze wprowadzone przez użytkownika, który nałożył zawieszenie, zaglądając do sekcji **Notatki dotyczące oszustwa** na skróconej karcie **Uwagi**.

Aby uzyskać więcej informacji na temat pracy z funkcją wstrzymywania zamówień, zobacz [Wstrzymania zamówień](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/work-with-order-holds).

