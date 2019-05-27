---
title: Limity kredytu dla odbiorców
description: Ten artykuł zawiera omówienie mechanizmu działania limitów kredytowe w Microsoft Dynamics 365 for Finance and Operations.
author: omulvad
manager: AnnBe
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fd7022eb1ed2671fcfc2861eb8ec7504ebf9f98
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551821"
---
# <a name="credit-limits-for-customers"></a>Limity kredytu dla odbiorców

[!include [banner](../includes/banner.md)]

Ustawienie limitu kredytu umożliwia określenie maksymalnej kwoty rozszerzenia kredytu dla odbiorców. Jeżeli określono limit kredytu, jest sprawdzany automatycznie, gdy użytkownik spróbuje zaktualizować dokument. W przypadku przekroczenia limitu kredytu wyświetlany jest komunikat dla użytkownika. Ten artykuł zawiera przegląd sposobu działania limitu kredytu i odpowiedzi na następujące pytania:

-   Dla jakich dokumentów i procesów mogę sprawdzić limit kredytu?

-   Gdzie skonfigurować sposób obliczania pozostałego kredytu odbiorcy?

-   Gdzie są używane informacje o pozostałym kredycie odbiorcy?

-   Gdzie określić, czy identyfikacja jest wymagana do rozszerzenia kredytu odbiorcy, a także kwotę limitu kredytu wymagającą identyfikacji?

-   Gdzie określić, czy ma być wyświetlane ostrzeżenie lub błąd po przekroczeniu limitu kredytu?

-   Jak określić limit kredytu dla danego odbiorcy?

-   Jak ręcznie sprawdzić limity kredytu w zamówieniach sprzedaży?

**Dla jakich dokumentów i procesów mogę sprawdzić limit kredytu?**

Użyj formularza **Parametry modułu rozrachunków z odbiorcami**, aby określić, dla których dokumentów sprawdzić limity kredytu. Aby wprowadzić zmiany w tym formularzu, musisz być członkiem roli zabezpieczeń Administrator systemu (-SYSADMIN-). Limity kredytu można sprawdzić dla następujących dokumentów i procesów:

-   Faktury dla zamówień sprzedaży po zaksięgowaniu faktur

-   Dokumenty dostawy dla zamówień sprzedaży po zaktualizowaniu dokumentów dostawy

-   Zamówienia sprzedaży po dodaniu wierszy w formularzu **Zamówienie sprzedaży**

-   Zamówienia sprzedaży po ich utworzeniu za pomocą usługi

-   Faktury niezależne po zaksięgowaniu faktur

Limity kredytu są sprawdzane automatycznie, jeżeli ustawiono jedną z następujących opcji:

-   W formularzu **Parametry modułu rozrachunków z odbiorcami** pole **Typ limitu kredytu** jest ustawione na wartość inną niż **Brak**. Limity kredytu są sprawdzane dla wszystkich odbiorców.

-   W formularzu **Parametry modułu rozrachunków z odbiorcami** pole **Typ limitu kredytu** jest ustawione na **Brak**, ale wybrano opcję **Wymagany limit kredytu** dla odbiorcy w formularzu **Klienci**. Limity kredytu są sprawdzane tylko dla określonych odbiorców.

Aby sprawdzić limity kredytu dla następujących dokumentów, należy określić dodatkowe ustawienia.

|    Wydruk pokwitowania                                    |    Ustawienie dodatkowe                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Faktura niezależna                         |    W formularzu Parametry modułu rozrachunków z odbiorcami, w obszarze Poziom kredytu wybierz opcję Sprawdzanie limitu kredytowego na fakturze niezależnej.     |
|    Zamówienie sprzedaży (wprowadzone ręcznie)            |    W formularzu Parametry modułu rozrachunków z odbiorcami, w obszarze Poziom kredytu wybierz opcję Sprawdzanie limitu kredytu na zamówieniu sprzedaży.           |
|    Zamówienie sprzedaży (otrzymane elektronicznie)     |    W formularzu Parametry modułu rozrachunków z odbiorcami, w obszarze AIF wybierz opcję Sprawdzanie limitu kredytu dla zamówień sprzedaży.                     |

**Gdzie skonfigurować sposób obliczania pozostałego kredytu odbiorcy?**

Usługę Dynamics 365 można skonfigurować do obliczania pozostałego kredytu odbiorcy w jeden z następujących sposobów:

-   Porównanie limitu kredytu z saldem odbiorcy.

-   Porównanie limitu kredytu z saldem odbiorcy i sumami dokumentów dostawy.

-   Porównanie limitu kredytu z saldem odbiorcy i wszystkimi działaniami dotyczącymi otwartych transakcji. Obejmuje to kwoty dokumentów dostawy i kwoty zamówień sprzedaży.

Użyj formularza **Parametry modułu rozrachunków z odbiorcami**, aby określić informacje, z którymi ma zostać przeprowadzone porównanie. Aby wprowadzić zmiany w tym formularzu, musisz być członkiem roli zabezpieczeń Administrator systemu (-SYSADMIN-). W polu **Typ limitu kredytu** wybierz, czy przeprowadzić sprawdzenia limitu kredytu i jakie informacje o transakcjach mają zostać uwzględnione przy sprawdzaniu limitu kredytu. Dostępne są następujące opcje:

-   **Brak** — nie sprawdzaj limitów kredytu. Tę opcję można pominąć dla wybranego odbiorcy, zaznaczając pole wyboru **Wymagany limit kredytu** w formularzu **Klienci**. Po wykonaniu tej czynności limit kredytu jest sprawdzany według salda odbiorcy.

-   **Saldo** — limit kredytu jest porównywany z saldem odbiorcy.

-   **Saldo + dokument dostawy lub dokument przyjęcia produktów** — limit kredytu jest porównywany z saldem odbiorcy i dostawami.

-   **Saldo + wszystko** — limit kredytu jest porównywany z saldem odbiorcy, dostawami i otwartymi zamówieniami.

**Gdzie są używane informacje o pozostałym kredycie odbiorcy?**

Informacje o saldzie odbiorcy i pozostałej kwocie kredytu są obliczane i zapisywane po utworzeniu migawki wiekowania i wyświetlane w formularzu **Windykacja**. Kwoty wyświetlane w formularzu **Windykacja** mogą nie obejmować wszystkich działań dotyczących transakcji do momentu utworzenia nowej migawki wiekowania. Aby uzyskać więcej informacji, zobacz temat [Windykacja i kredyt w rozrachunkach z odbiorcami](https://technet.microsoft.com/en-us/library/hh209221.aspx).

W zależności od wybranych dokumentów informacje o saldzie odbiorcy i pozostałej kwocie kredytu są obliczane po aktualizacji zamówień sprzedaży, dokumentów dostawy i faktur odbiorcy. Jeżeli kwota używanego dokumentu może spowodować przekroczenie limitu kredytu, wyświetlany jest komunikat.

**Gdzie określić, czy identyfikacja jest wymagana do rozszerzenia kredytu odbiorcy, a także limit kredytu wymagający identyfikacji?**

Użyj formularza **Parametry modułu rozrachunków z odbiorcami**, aby określić, czy wymagać identyfikacji i kwotę limitu kredytu, która wymaga identyfikacji.
Aby wprowadzić zmiany w tym formularzu, musisz być członkiem roli zabezpieczeń Administrator systemu (-SYSADMIN-).

|    Pole                                    |    opis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Wymagaj identyfikacji wraz z kredytem     |    Umożliwia wybór typu identyfikacji, która musi być wprowadzona dla odbiorców, którym firma zwiększa kredyt. Opcja wybrana w tym polu określa kiedy i jakiego typu informacje są wymagane w polach Identyfikacja urzędowa w formularzu Odbiorcy: Nie – Nie jest wymagana identyfikacja urzędowa, niezależnie od limitu kredytowego odbiorcy.     Tak — wymagany jest numer dowodu osobistego wydanego urzędowo lub inny rodzaj urzędowego dokumentu, jeśli limit kredytowy odbiorcy jest większy od zera lub równy zero.     Dolny limit — wymagany jest numer dowodu osobistego wydanego urzędowo lub inny rodzaj urzędowego dokumentu, jeśli limit kredytu odbiorcy jest wyższy od limitu wprowadzonego w polu Limit tego formularza lub równy mu.        |
|    Limit                                    |    Należy podać limit kredytowy, przy którym odbiorca musi przedstawić numer dowodu osobistego wydanego urzędowo lub inny rodzaj urzędowego dokumentu.    Na przykład należy wpisać 2000, aby było wymagane podanie numeru identyfikacyjnego, na przykład dowodu osobistego, przez odbiorców mających limit kredytowy w wysokości 2000 lub wyższy.    To pole jest dostępne tylko wtedy, gdy wartość Dolny limit jest wybrana w polu Wymagaj identyfikacji wraz z kredytem.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Gdzie określić, czy ma być wyświetlane ostrzeżenie lub błąd po przekroczeniu limitu kredytu?**

Użyj formularza **Parametry modułu rozrachunków z odbiorcami**, aby określić, czy wyświetlać ostrzeżenie lub błąd, jeżeli przekroczono limit kredytu. To ostrzeżenie lub błąd jest wyświetlane, gdy użytkownik wprowadza lub księguje informacje lub są one dodawane do dziennika, jeżeli dokumenty są przetwarzane przez usługę elektroniczną. Aby wprowadzić zmiany w tym formularzu, musisz być członkiem roli zabezpieczeń Administrator systemu (-SYSADMIN-).

|    Pole                                                               |    opis                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Komunikat po przekroczeniu limitu kredytu (w obszarze Poziom kredytu)     |    Należy wybrać, w jaki sposób wyświetlane są komunikaty dla użytkowników o przekroczeniu limitów kredytu. Należy wybrać jedną z następujących opcji: Błąd — wyświetlany jest komunikat o błędzie. Zwykle powoduje to zatrzymanie bieżącej operacji, a konflikt musi zostać rozwiązany przed kontynuacją przetwarzania.     Ostrzeżenie — wyświetlane jest ostrzeżenie, ale przetwarzanie może być kontynuowane.                     |
|    Komunikat po przekroczeniu limitu kredytu (w obszarze AIF)               |    Umożliwia wybór sposobu dostarczania komunikatów o przekroczeniu limitów kredytu w dzienniku: Wybierz jedną z następujących opcji: Błąd — komunikat o błędzie jest wyświetlany w formularzu Wyjątki, a dokument nie zostanie przetworzony do momentu usunięcia błędu.     Ostrzeżenie — w formularzu Wyjątki wyświetlane jest ostrzeżenie, ale przetwarzanie może być kontynuowane.        |

**Jak określić kwotę limit kredytu dla danego odbiorcy?**

Użyj formularza **Odbiorcy**, aby określić kwotę limitu kredytu dla określonego odbiorcy. Użytkownik musi być członkiem roli zabezpieczeń, do której przypisano obowiązek Obsługa danych głównych odbiorcy (CustCustomersMaintain), aby wprowadzić zmiany w tym formularzu.

1.  Kliknij kolejno opcję **Rozrachunki z odbiorcami** \> **Wspólny** \> **Odbiorcy** \> **Wszyscy odbiorcy**. Kliknij dwukrotnie konto odbiorcy.

2.  W formularzu **Odbiorcy**, w okienku akcji, kliknij opcję **Edytuj**.

3.  Wprowadź kwotę waluty w polu **Limit kredytu**. Ta wartość musi być większa od zera (0) i będzie używana jako kwota limitu kredytu.

4.  Jeżeli jest to wymagane, wprowadź numer dowodu osobistego wydanego urzędowo lub inny rodzaj urzędowego dokumentu w polu **Identyfikacja urzędowa**.

> [!NOTE]
> Typ limitu kredytu zwykle wybiera się w formularzu **Parametry modułu rozrachunków z odbiorcami**. Jednakże, jeżeli typ limitu kredytu jest ustawiony na **Brak**, należy także zaznaczyć pole wyboru **Wymagany limit kredytu** w formularzu **Odbiorcy** w celu sprawdzenia limitu kredytu względem salda odbiorcy. Aby uzyskać więcej informacji o typach limitu kredytu, zobacz sekcję „Dla jakich dokumentów i procesów mogę sprawdzić limit kredytu?” w tym temacie. 

**Jak sprawdzić ręcznie limity kredytu w zamówieniach sprzedaży?**

Czasami konieczne może być ręczne sprawdzenie limitu kredytu odbiorcy. Limit kredytu odbiorcy można na przykład sprawdzić ręcznie przed rozpoczęciem wprowadzania zamówienia sprzedaży. W celu ręcznego sprawdzenia limitów kredytu można użyć formularza **Zamówienie sprzedaży**. Użytkownik musi być członkiem roli zabezpieczeń, do której przypisano obowiązek Obsługa zamówienia sprzedaży (SalesOrderMaintain), aby wprowadzić zmiany w tym formularzu.

1.  Kliknij kolejno opcje **Sprzedaż i marketing** \> **Wspólne** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**. Kliknij dwukrotnie na zamówienie sprzedaży.

2.  W formularzu **Zamówienie sprzedaży**, w okienku akcji, na karcie **Zarządzaj** kliknij opcję **Sprawdzanie limitu kredytu**.
