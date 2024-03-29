---
title: Konfigurowanie miejsc docelowych raportowania elektronicznego zależnych od akcji
description: Ten artykuł objaśnia konfigurowanie miejsc docelowych zależnych od akcji dla formatu raportowania elektronicznego (ER) skonfigurowanych do generowania dokumentów wychodzących.
author: kfend
ms.date: 12/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 80a432a431891c02e4bf5c71cfe2bd9642c41c75
ms.sourcegitcommit: e9000d0716f7fa45175b03477c533a9df2bfe96d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/13/2022
ms.locfileid: "9843805"
---
# <a name="configure-action-dependent-er-destinations"></a>Konfigurowanie miejsc docelowych raportowania elektronicznego zależnych od akcji

[!include [banner](../includes/banner.md)]

Możesz skonfigurować [miejsca docelowe](electronic-reporting-destinations.md) dla każdej konfiguracji formatu składników wyjściowych (folderów lub plików) [raportowania elektronicznego](general-electronic-reporting.md) (ER) używanych do [generowania](general-electronic-reporting.md#Configuration) dokumentów wychodzących. Użytkownicy, którzy uruchamiają format ER tego typu i mają odpowiednie prawa dostępu, mogą również zmieniać skonfigurowane ustawienia miejsc docelowych w czasie wykonywania.

W wersji rozwiązania Microsoft Dynamics 365 Finance **10.0.17 i nowszej** format ER można uruchomić, [aprowizując ](er-apis-app10-0-17.md) kod akcji, który użytkownik wykonuje, uruchamiając ten format ER. Na przykład w module **Rozrachunki z odbiorcami** w ustawieniach zarządzania drukowaniem można wybrać format ER generujący określony dokument biznesowy, na przykład fakturę niezależną. Następnie można wybrać **Widok**, aby wyświetlić podgląd faktury, lub przycisk **Drukuj**, aby wysłać ją do drukarki. Jeśli akcja użytkownika jest przekazywana w czasie wykonywania dla uruchomionego formatu ER, można skonfigurować różne miejsca docelowe ER dla różnych akcji użytkowników. W tym artykule opisano sposób konfigurowania miejsc docelowych ER dla tego typu formatu ER.

## <a name="make-action-dependent-er-destinations-available"></a>Udostępnianie miejsc docelowych raportowania elektronicznego zależnych od akcji

Aby skonfigurować miejsca docelowe ER zależne od akcji w bieżącym wystąpieniu aplikacji Finance i włączyć [nowy](er-apis-app10-0-17.md) interfejs API ER, otwórz obszar roboczy [Zarządzanie funkcjami](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) i włącz funkcję **Konfiguruj określone miejsca docelowe ER, które mają być używane dla różnych akcji PM**. Aby użyć skonfigurowanych miejsc docelowych ER do określonych raportów w czasie wykonywania, włącz funkcję **Przekieruj dane wyjściowe raportów PM na podstawie miejsc docelowych ER charakterystycznych dla akcji użytkownika (grupa czynności 1)**.

## <a name="configure-action-dependent-er-destinations"></a>Konfigurowanie miejsc docelowych raportowania elektronicznego zależnych od akcji

Po włączeniu funkcji **Konfiguruj określone miejsca docelowe ER do użycia dla różnych funkcji akcji PM** można skonfigurować zależne od akcji miejsca docelowe raportowania elektronicznego na skróconej karcie **Miejsce docelowe pliku** na stronie **Miejsce docelowe raportowania elektronicznego**. Dla każdego składnika można dodać rekord i włączyć określone miejsca docelowe ER. Dla każdego rekordu należy określić typ dokumentu, do których mają zostać zastosowane skonfigurowane miejsca docelowe ER. W polu **Typ dokumentu** wybierz jedną z następujących wartości:

- Wybierz opcję **Elektroniczne**, aby zastosować skonfigurowane miejsca docelowe, jeśli nie zostanie podany kod akcji użytkownika w czasie wykonywania.
- Wybierz opcję **Zarządzanie drukowaniem**, aby zastosować skonfigurowane miejsca docelowe, jeśli zostanie podany kod akcji użytkownika w czasie wykonywania.
- Wybierz opcję **Dowolne**, aby zawsze stosować skonfigurowane miejsca docelowe, bez względu na to, czy zostanie podany kod akcji użytkownika w czasie wykonywania.

W przypadku wybrania typu dokumentu **Zarządzanie drukowaniem** należy określić akcje użytkownika, dla których mają zostać zastosowane skonfigurowane miejsca docelowe ER. W polu **Akcja zarządzania drukowaniem** wybierz jedną z następujących wartości:

- Wybierz opcję **Wyświetl**, aby zastosować skonfigurowane miejsca docelowe, jeśli w czasie wykonywania zostanie wybrana akcja **Wyświetl**.
- Wybierz opcję **Drukuj**, aby zastosować skonfigurowane miejsca docelowe, jeśli w czasie wykonywania zostanie wybrana akcja **Drukuj**.
- Wybierz opcję **Wyślij**, aby zastosować skonfigurowane miejsca docelowe, jeśli w czasie wykonywania zostanie wybrana akcja **Wyślij**.

> [!NOTE]
> Można wybrać wiele akcji dla jednego rekordu miejsca docelowego.

W przypadku wybrania typu dokumentu **Dowolny** akcja **Automatyczne wykrywanie** jest wybierana automatycznie w polu **Akcja zarządzania drukowaniem** jako akcja użytkownika i ma miejsce następujące zachowanie:

- Jeśli w czasie wykonywania nie zostanie podany kod akcji użytkownika, są stosowane wszystkie skonfigurowane miejsca docelowe ER,
- Jeśli w czasie wykonywania zostanie podany kod akcji użytkownika, jest stosowane miejsce docelowe ER wstępnie zdefiniowane dla określonej akcji, **niezależnie od tego, czy zostało włączone**:

    - Jeśli w czasie wykonywania zostanie podana akcja **Wyświetl**, jest stosowane miejsce docelowe ER **Ekran**.
    - Jeśli w czasie wykonywania zostanie podana akcja **Wyświetl**, jest stosowane miejsce docelowe ER **Poczta e-mail**.
    - Jeśli w czasie wykonywania zostanie podana akcja **Drukuj**, jest stosowane miejsce docelowe ER **Drukarka**.

Można na przykład użyć formatu ER **Faktura niezależna (Excel)** w celu wydrukowania [faktury niezależnej](../../../finance/accounts-receivable/create-free-text-invoice-new.md) podczas jej księgowania. Aby rozsyłać wygenerowany dokument, należy skonfigurować miejsca docelowe ER dla tego formatu ER. Może być na przykład konieczne skonfigurowanie miejsc docelowych ER, aby w wygenerowanym dokumencie wykonać następujące czynności:

- Archiwizuj dokument, jeśli zostanie uruchomiony format ER, ale nie zostanie podany kod akcji (na przykład przy wysłaniu dokumentu drogą elektroniczną).
- Wyświetl podgląd dokumentu w przeglądarce internetowej, gdy użytkownik wykonuje akcję **Wyświetl**.
- Archiwizuj i wydrukuj dokument, gdy użytkownik wykonuje akcję **Drukuj**.
- Archiwizuj dokument i wyślij go pocztą e-mail jako załącznik do wychodzącej wiadomości e-mail, gdy użytkownik wykonuje akcję **Wyślij**.

Na poniższej ilustracji pokazano, jak można używać tego sposobu konfigurowania miejsc docelowych ER jako zestawu pojedynczych rekordów docelowych, gdy każdy rekord jest konfigurowany jako indywidualna akcja użytkownika:

![Strona miejsca docelowego raportowania elektronicznego, która ma zależne od akcji ustawienia miejsc docelowych dla formatu ER, gdy każdy rekord docelowy jest skonfigurowany dla pojedynczej akcji użytkownika.](./media/er-destination-action-dependent-01.png)

Na poniższej ilustracji pokazano, jak można używać alternatywnego sposobu konfigurowania miejsc docelowych ER jako zestawu pojedynczych rekordów docelowych, gdy każdy rekord jest konfigurowany jako indywidualne miejsce docelowe:

![Strona miejsca docelowego raportowania elektronicznego, która ma zależne od akcji ustawienia miejsc docelowych dla formatu ER, gdy każdy rekord docelowy jest skonfigurowany dla pojedynczego miejsca docelowego.](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Jeśli dla uruchomionego formatu ER zostanie podany kod akcji, ale dla tego kodu akcji nie skonfigurowano miejsc docelowych, stosowane jest [domyślne](electronic-reporting-destinations.md#default-behavior) zachowania dla miejsca docelowego.

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Zmienianie miejsc docelowych raportowania elektronicznego zależnych od akcji w czasie wykonywania

W przypadku uruchomienia formatu ER przez użytkownika mającego odpowiednie [uprawnienia](electronic-reporting-destinations.md#security-considerations) do zmieniania skonfigurowanych ustawień miejsc docelowych w czasie wykonywania wyświetlane jest okno dialogowe z opcją zmiany skonfigurowanych ustawień miejsc docelowych. To okno dialogowe jest opcjonalne, a jego wygląd zależy od sposobu zaimplementowania wywołania struktury ER służącego do uruchamiania formatu ER. Jeśli to okno dialogowe zostanie wyświetlone, miejsca docelowe ER w tym oknie będą włączone zgodnie z podaną akcją użytkownika.

Na poniższej ilustracji przedstawiono przykład okna dialogowego **Miejsca docelowe formatu raportowania elektronicznego**, które jest wyświetlane po [zaksięgowaniu](../../../finance/accounts-receivable/create-free-text-invoice-new.md) faktury niezależnej i uruchomieniu formatu ER **Faktura niezależna (Excel)** w celu wygenerowania tego dokumentu, jeśli dla tego formatu aprowizowano akcję **Drukarka** i skonfigurowano miejsca docelowe ER, tak jak pokazano wcześniej w tym artykule.

![Okno dialogowe z opcją zmiany początkowych skonfigurowanych miejsc docelowych ER dla uruchomionego formatu ER.](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> W przypadku skonfigurowania miejsc docelowych ER dla kilku składników uruchomionego formatu ER, opcja będzie dostępna oddzielnie dla każdego skonfigurowanego składnika formatu ER.

Jeśli kilka formatów ER ma zastosowanie jako szablony raportów dla wybranego dokumentu, wszystkie miejsca docelowe ER dla wszystkich mających zastosowanie szablonów raportów ER są pokazane w oknie dialogowym i dostępne do ręcznego dostosowania w czasie pracy.

Jeśli do wybranego dokumentu nie mają zastosowania szablony raportów [SQL Server Reporting Services (SSRS)](SSRS-report.md), standardowy wybór miejsc docelowych zarządzania drukowaniem jest dynamicznie ukrywany.

Od wersji Finance **10.0.31** możesz ręcznie zmienić przypisane miejsca docelowe ER w czasie pracy dla następujących dokumentów biznesowych:

- Wyciąg z konta odbiorcy
- Nota odsetkowa
- Tekst ponaglenia
- Wskazówka dotycząca płatności przez klienta
- Zawiadomienie o płatności dostawcy

Aby aktywować możliwość zmiany miejsc docelowych ER w czasie rzeczywistym, włącz funkcję **Umożliwienie dostosowania miejsc przeznaczenia ER w czasie uruchomienia** w przestrzeni roboczej [Zarządzanie funkcjami](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace).

> [!IMPORTANT]
> W przypadku raportów **Deklaracja płatności klienta** i **Deklaracja płatności dostawcy** możliwość ręcznej zmiany miejsc docelowych ER jest dostępna tylko wtedy, gdy włączone jest **ForcePrintJobSettings**.

[![Dostosowanie miejsc docelowych ER w czasie biegu.](./media/ERdestinaiotnChangeUI.jpg)](./media/ERdestinaiotnChangeUI.jpg)

> [!NOTE]
> Gdy opcja **Użyj miejsca docelowego zarządzania drukiem** jest ustawiona na **Tak**, system używa domyślnych miejsc docelowych ER, które są skonfigurowane dla określonych raportów ER. Wszystkie ręczne zmiany dokonywane w oknie dialogowym są ignorowane. Ustaw opcję **Użyj miejsc docelowych zarządzania drukiem** na **Nie**, aby przetwarzać dokumenty w miejscach docelowych ER, które są zdefiniowane w oknie dialogowym bezpośrednio przed uruchomieniem raportów.

Poniższe dokumenty biznesowe nie zakładają jawnego wyboru akcji przez użytkownika podczas ich uruchamiania:

- Wyciąg z konta odbiorcy
- Nota odsetkowa
- Tekst ponaglenia
- Wskazówka dotycząca płatności przez klienta
- Zawiadomienie o płatności dostawcy

W celu określenia, które działanie jest wykorzystywane podczas przetwarzania poprzednich raportów, stosuje się następującą logikę:

- Jeśli jest włączone **ForcePrintJobSettings**:

    - Jeśli opcja **Użyj miejsca docelowego zarządzania drukiem** jest ustawiona na **Tak**, używana jest akcja **Drukuj**.
    - Jeśli opcja **Użyj miejsca docelowego zarządzania drukiem** jest ustawiona na **Nie**, używana jest akcja **Wyświetl**.

- Jeśli nie jest włączone **ForcePrintJobSettings**:

    - Jeśli opcja **Użyj miejsca docelowego zarządzania drukiem** jest ustawiona na **Tak**, akcja **Drukuj** jest używana dla raportów **Deklaracja płatności klienta** i **Deklaracja płatności dostawcy**.
    - Jeśli opcja **Użyj miejsca docelowego zarządzania drukiem** jest ustawiona na **Nie**, domyślny szablon raportu SSRS jest zawsze używany dla raportów **Deklaracja płatności klienta** i **Deklaracja płatności dostawcy**, niezależnie od jakichkolwiek skonfigurowanych ustawień ER.
    - Akcja **Drukuj** jest zawsze używana dla raportów **Wyciąg z konta klienta**, **Nota odsetkowa** oraz **Nota listowa do inkasenta**.

W przypadku logiki poprzedniej akcje **Drukowania** lub **Wyświetlania** mogą być używane do konfigurowania lokalizacji docelowych raportów ER zależnych od akcji. W czasie pracy w oknie dialogowym filtrowane są tylko miejsca docelowe ER, które są skonfigurowane dla określonej akcji.

## <a name="verify-the-provided-user-action"></a>Weryfikowanie podanej akcji użytkownika

Podczas wykonywania określonej akcji użytkownika można sprawdzić, jaka akcja użytkownika ma być uruchomiona w formacie ER (jeśli ma to zastosowanie). Ta weryfikacja jest ważna, jeśli trzeba skonfigurować miejsca docelowe ER zależne od akcji, ale nie masz pewności, który kod akcji użytkownika zostanie podany (jeśli istnieje). Na przykład, gdy rozpoczniesz księgowanie faktury niezależnej i ustawisz opcję **Drukuj fakturę** na wartość **Tak** w oknie dialogowym **Księgowanie faktury niezależnej**, możesz ustawić opcję **Użyj miejsca docelowego zarządzania drukowaniem** na wartość **Tak** lub **Nie**.

Aby sprawdzić podany kod akcji użytkownika, należy wykonać następujące kroki.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **Parametry użytkownika** [ustaw](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) opcję **Uruchom w trybie debugowana** na **Tak**.
4. Wykonaj akcję użytkownika, uruchamiając format ER. Należy pamiętać, że parametry użytkownika ER są właściwe dla firmy i właściwe dla użytkownika.
5. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Dzienniki debugowania konfiguracji**.
6. Na stronie **Dzienniki debugowania konfiguracji** odfiltruj dzienniki uruchamiania ER, aby znaleźć dziennik uruchomienia formatu ER.
7. Przejrzyj wpisy dziennika, które muszą zawierać rekord prezentujący podany kod akcji użytkownika, jeśli na potrzeby uruchomienia formatu ER wybrano dowolną akcję.

    ![Raportowanie elektroniczne uruchamia stronę dzienników zawierającą informacje o kodzie akcji użytkownika podanym dla odfiltrowanego uruchomienia formatu ER.](./media/er-destination-action-dependent-03.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)

[Zmiany w interfejsie API struktury raportowania elektronicznego w aktualizacji Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
