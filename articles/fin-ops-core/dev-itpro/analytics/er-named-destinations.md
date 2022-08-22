---
title: Konfigurowanie zależnych od rekordu miejsc docelowych raportowania elektronicznego zarządzania drukowaniem
description: W tym artykule wyjaśniono sposób konfigurowania miejsc docelowych zarządzania drukowaniem zależnych od rekordu dla formatu raportowania elektronicznego (ER) skonfigurowanych do generowania dokumentów wychodzących.
author: kfend
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.form: ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 7c92d580f6adebdba12b7964a42fd4752e9c9205
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285070"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Konfigurowanie zależnych od rekordu miejsc docelowych raportowania elektronicznego zarządzania drukowaniem

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, w jaki sposób użytkownik występujący w roli Administrator systemu lub Pracownik ds. płatności rozrachunków z odbiorcami może wykonywać następujące zadania:

- Konfigurowanie nazwanych miejsc docelowych [raportowania elektronicznego (ER)](general-electronic-reporting.md) rozwiązania ER, które generuje faktury niezależne.
- Przypisywanie miejsca docelowego ER do jednego rekordu [zarządzania drukowaniem](document-reporting-services.md).

Te procedury można wykonać na danych firmy USMF. Nie są wymagane umiejętności kodowania.

## <a name="introduction"></a>Wprowadzenie

Możesz skonfigurować [miejsca docelowe](electronic-reporting-destinations.md) dla każdego folderu w składniku pliku wyjściowego [konfiguracji](general-electronic-reporting.md#Configuration) [formatu](general-electronic-reporting.md) ER, która jest używana do generowania dokumentów wychodzących. Jeśli uruchamiasz format ER tego typu i masz odpowiednie prawa dostępu, możesz również zmieniać skonfigurowane ustawienia miejsc docelowych w czasie wykonywania.

W wersji rozwiązania Microsoft Dynamics 365 Finance **10.0.17 i nowszej** można [skonfigurować](er-apis-app10-0-17.md) kod akcji dla formatu ER w celu określenia akcji wykonywanej przez użytkowników, którzy uruchamiają ten format ER. Na przykład w module **Rozrachunki z odbiorcami** w ustawieniach zarządzania drukowaniem można wybrać format ER generujący określony dokument biznesowy, na przykład fakturę niezależną. Następnie można wybrać **Widok**, aby wyświetlić podgląd faktury, lub przycisk **Drukuj**, aby wysłać ją do drukarki. Jeśli akcja jest przekazywana w czasie wykonywania dla uruchomionego formatu ER, można [skonfigurować różne miejsca docelowe ER dla różnych akcji użytkowników](er-action-dependent-destinations.md).

W Finance **w wersji 10.0.21 i nowszej** można [skonfigurować](er-apis-app10-0-21.md) nazwane miejsce docelowe dla formatu ER i przypisać je do rekordu zarządzania drukowaniem, który jest przetwarzany podczas wykonywania tego formatu ER. Na przykład w module **Rozrachunki z odbiorcami** w ustawieniach zarządzania drukowaniem możesz skonfigurować rekord **Oryginał**, aby wykonywać następujące akcje:

- Wykonywanie formatu ER.
- Wysyłanie do odbiorcy wiadomości e-mail z wygenerowaną fakturą.
- Konfigurowanie rekordu **Kopia** w celu wykonywania tego samego formatu.
- Drukowanie kopii faktury na drukarce sieciowej.

W takim przypadku należy skonfigurować różne miejsca docelowe ER dla uruchomionego formatu ER, a także wybrać miejsca docelowe dla różnych rekordów zarządzania drukowaniem.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem musi zostać włączona funkcja **Zezwól na konfigurowanie miejsc docelowych ER zależnie od elementu zarządzania drukowaniem** w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace). Należy również zmienić kod źródłowy, aby umożliwić konfigurację nazwanych miejsc docelowych ER w bieżącym wystąpieniu Finance i włączenie [nowego](er-apis-app10-0-21.md) interfejsu API ER.

Ponadto do wystąpienia Finance należy [zaimportować](er-download-configurations-global-repo.md) konfigurację ER **faktury niezależnej (Excel)**.

## <a name="configure-a-new-er-destination"></a>Konfigurowanie nowego miejsca docelowego raportowania elektronicznego

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami** \> **Faktury** \> **Wszystkie faktury niezależne**.
2. Wybierz fakturę dla konta odbiorcy **US-001**.
3. Na stronie **Faktura niezależna**, na karcie **Faktura**, w grupie **Zarządzanie drukowaniem** wybierz pozycję **Zarządzanie drukowaniem**.
4. Na stronie **Ustawienia zarządzania drukowaniem** rozwiń węzły **Moduł — rozrachunki z odbiorcami** \> **Dokumenty** \> **Faktura niezależna**, wybierz rekord **Oryginalna**, a następnie wykonaj następujące kroki.

    1.  Należy przestrzegać bieżących ustawień wybranego rekordu:
        -   Domyślny raport SSRS **FreeTextInvoice.Report** jest wybrany w polu **Format raportu**.
        -   Nazwa **\<Default\>** jest wyświetlana w polu **Miejsce docelowe** informując, że dla przypisanego raportu SSRS nie wybrano niestandardowego miejsca docelowego. 
    2.  W polu **Format raportu** wybierz konfigurację formatu ER **Faktura niezależna (Excel)** .
        -   Nazwa pola **Miejsce docelowe** zostanie zmienione na wartość **Nazwa miejsca docelowego**.
        -   Nazwa **\<No named destination\>** jest wyświetlana w polu **Nazwa miejsca docelowego** informując, że dla przypisanego formatu ER nie wybrano nazwanego miejsca docelowego.
    3.  Naciśnij przycisk strzałki po prawej stronie pola **Nazwa miejsca docelowego**.    
    4. Na stronie **Nazwane miejsce docelowe raportowania elektronicznego** w polu **Nazwa** wprowadź **Główne miejsce docelowe**.
    5. Wybierz opcję **Zapisz**.
    6. Na skróconej karcie **Miejsce docelowe pliku** [skonfiguruj](er-destination-type-email.md) miejsce docelowe **Wiadomość e-mail** dla składnika **Raport**.
    7. Zamknij stronę **Nazwane miejsce docelowe raportowania elektronicznego**.
    8. Na stronie **Konfiguracja zarządzania drukowaniem** w polu **Nazwa miejsca docelowego** wybierz nazwane miejsce docelowe **Główne miejsce docelowe**.

    ![Konfigurowanie nazwanego miejsca docelowego ER wybranego formatu ER i przypisywanie go do skonfigurowanego rekordu zarządzania drukowaniem na stronie Konfiguracja zarządzania drukowaniem](./media/er-named-destinations-01.gif)

    Masz teraz skonfigurowane nazwane miejsce docelowe ER **Główne miejsce docelowe** formatu **Faktura niezależna (Excel)**, które jest przypisane do rekordu zarządzania drukowaniem **Oryginalne** w obszarze **Moduł — rozrachunki z odbiorcami** \> **Dokumenty** \> **Faktura niezależna**.

5. Rozwiń węzły **Moduł — rozrachunki z odbiorcami** \> **Konto — US-001** \> **Faktura niezależna**, wybierz rekord **Oryginalna**, a następnie wykonaj następujące kroki.

    1. Zaznacz rekord i przytrzymaj go (lub kliknij prawym przyciskiem myszy), a następnie wybierz opcję **Zastąp**.
    2. Naciśnij przycisk strzałki po prawej stronie pola **Nazwa miejsca docelowego**.
    3. Na stronie **Nazwane miejsce docelowe raportowania elektronicznego** w okienku akcji naciśnij przycisk **Nowe**.
    4. W polu **Nazwa** wpisz **Miejsce docelowe US-001**.
    5. Na skróconej karcie **Miejsce docelowe pliku** [skonfiguruj](er-destination-type-print.md) miejsce docelowe **Drukarka** dla składnika **Raport**.
    6. Zamknij stronę **Nazwane miejsce docelowe raportowania elektronicznego**.
    7. Na stronie **Konfiguracja zarządzania drukowaniem** w polu **Nazwa miejsca docelowego** wybierz nazwane miejsce docelowe **Miejsce docelowe US-001**.

    ![Konfigurowanie nazwanego miejsca docelowego ER wybranego formatu ER i przypisywanie go do skonfigurowanego rekordu zarządzania drukowaniem na stronie Konfiguracja zarządzania drukowaniem](./media/er-named-destinations-02.gif)

    Masz teraz skonfigurowane nazwane miejsce docelowe ER **Miejsce docelowe US-001** formatu **Faktura niezależna (Excel)**, które jest przypisane do rekordu zarządzania drukowaniem **Oryginalne** w obszarze **Moduł — rozrachunki z odbiorcami** \> **Konto — US-001** \> **Faktura niezależna**.

Teraz, podczas przetwarzania faktury niezależnej jest wykonywany format ER **Faktura niezależna (Excel)** i występuje jedno z następujących zdarzeń:

- Jeśli faktura niezależna jest przeznaczona dla odbiorcy innego niż US-001, wygenerowany dokument jest wysyłany pocztą e-mail.
- Jeśli faktura niezależna jest przeznaczona dla odbiorcy US-001, wygenerowany dokument jest drukowany.

> [!NOTE]
> Jeśli nazwane miejsce docelowe nie zostanie skonfigurowane dla rekordu zarządzania drukowaniem podczas wykonywania i dla wykonywanego formatu ER są dostępne domyślne miejsca docelowe ER, zostaną one użyte.

> [!IMPORTANT]
> Jeśli na stronie **Miejsca docelowe raportowania elektronicznego** (**Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Miejsce docelowe raportowania elektronicznego**) wybierzesz format ER, dla którego skonfigurowano co najmniej jedno nazwane miejsce docelowe, otrzymasz powiadomienie o istnieniu nazwanych miejsc docelowych.
>
> ![Powiadomienie o istnieniu skonfigurowanych nazwanych miejsc docelowych dla wybranego formatu ER na stronie miejsca docelowego raportowania elektronicznego](./media/er-named-destinations-03.png)
>
> Usunięcie domyślnego miejsca docelowego powoduje również usunięcie wszystkich nazwanych miejsc docelowych. Jeśli nazwane miejsca docelowe zostały wybrane dla rekordów zarządzania drukowaniem, wybór tych nazwanych miejsc docelowych jest anulowany.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Kopiowanie istniejącego miejsca docelowego ER jako nowego nazwanego miejsca docelowego

Gdy dla formatu ER jest dostępne domyślne nazwane miejsce docelowe ER, można go użyć jako szablonu dla nowych miejsc docelowych ER. Aby utworzyć nowe miejsce docelowe raportowania elektronicznego oparte na domyślnym miejscu docelowym, wybierz pozycję **Kopiuj z domyślnego** na stronie **Nazwane miejsce docelowe raportowania elektronicznego**. Nowe miejsce docelowe nazywa się **Domyślne**. Możesz powtórzyć ten krok, ile razy jest to wymagane.

Jako szablon nowego nazwanego miejsca docelowego można wybrać dowolne istniejące nazwane miejsce docelowe. Aby utworzyć nowe nazwane miejsce docelowe raportowania elektronicznego oparte na wybranym nazwanym miejscu docelowym, wybierz pozycję **Kopiuj** na stronie **Nazwane miejsce docelowe raportowania elektronicznego**. Nazwa nowego miejsca docelowego jest taka sama jak nazwa wybranego miejsca docelowego, ale z sufiksem „Kopia”. Możesz powtórzyć ten krok, ile razy jest to wymagane.

## <a name="security-considerations"></a>Zagadnienia dotyczące zabezpieczeń

Nazwane miejsca docelowe ER można skonfigurować na stronie **Konfiguracja zarządzania drukowaniem** tylko wtedy, gdy użytkownik ma [uprawnienie](../sysadmin/role-based-security.md#permissions) do wykonania tego zadania. Uprawnienia można przyznać, jeśli [obowiązek](../sysadmin/role-based-security.md#duties) **Konfigurowanie miejsca docelowego formatu raportowania elektronicznego** zostanie przypisany do jednej z [ról zabezpieczeń](../sysadmin/role-based-security.md#security-roles). Więcej informacji zawiera temat [Zagadnienia dotyczące zabezpieczeń](electronic-reporting-destinations.md#security-considerations).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)

[Zmiany w interfejsie API struktury raportowania elektronicznego w aktualizacji Application update 10.0.17](er-apis-app10-0-17.md)

[Zmiany w interfejsie API struktury raportowania elektronicznego w aktualizacji Application update 10.0.21](er-apis-app10-0-21.md)

[Zmienianie kodu, aby użytkownicy mogli konfigurować nazwane miejsca docelowe ER i korzystać z nich](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
