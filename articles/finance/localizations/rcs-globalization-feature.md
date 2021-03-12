---
title: Usługi Regulatory Configuration Services (RCS) — funkcje globalizacji
description: W tym temacie objaśniono sposób korzystania z Microsoft Regulatory Configuration Services (RCS) i repozytorium globalnego do tworzenia i obsługiwania funkcji globalizacji.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: b701e6bfa14ac30e02bfe79666963db4ee657302
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002801"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Usługi Regulatory Configuration Services (RCS) — funkcje globalizacji

[!include [banner](../includes/banner.md)]

Za pomocą usług Microsoft Regulatory Configuration Services (RCS) można utworzyć funkcję Globalizacji, której można używać w usługach globalizacji, takich jak usługa fakturowania elektronicznego. RCS umożliwia wykonywanie następujących zadań:

- Definiowanie powiązanych składników funkcji.
- Zarządzanie cyklem życia funkcji za pomocą stanu funkcji.
- Umożliwia udostępnienie funkcji dla zdefiniowanych środowisk.
- Udostępnianie funkcji innym organizacjom.

Poniższe procedury dotyczą sposobu dodawania funkcji globalizacji i związanych z nimi składników przez użytkownika z RCS, aktualizowania stanu funkcji oraz udostępniania funkcji w taki sposób, aby mogły być używane w usługach globalizacji.

Przed wykonaniem tych procedur należy wykonać kroki związane z następującymi zadaniami:

- Uzyskanie dostępu do wystąpienia RCS.
- Tworzenie i uaktywnianie dostawcy konfiguracji. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

W wystąpieniu aplikacji Finance and Operations wykonaj następujące kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.

> [!NOTE]
> Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać dostęp do środowiska, wybierając opcję logowania.

## <a name="turn-on-the-globalization-features"></a>Włączanie funkcji globalizacji

1. W wystąpieniu RCS wybierz kafelek **Zarządzanie funkcjami**.
2. W obszarze roboczym **Zarządzanie funkcjami** wybierz z listy **Funkcje globalizacji**, a następnie wybierz pozycję **Włącz teraz**.

    ![Funkcje globalizacji w zarządzaniu funkcjami](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Funkcje globalizacji

Aby skorzystać z funkcji globalizacji, należy najpierw zaimportować ją z repozytorium globalnego i utworzyć własną wersję. Istnieją dwa sposoby dodawania funkcji globalizacji:

- Dodaj pochodną funkcję opartą na istniejącej funkcji, która została opublikowana lub udostępniona.
- Dodaj nową funkcję utworzoną przez użytkownika od podstaw.

## <a name="access-globalization-features"></a>Dostęp do funkcji globalizacji

1. Należy się upewnić, że funkcja **Funkcje globalizacji** jest włączona w module Zarządzanie funkcjami, tak jak to opisano wcześniej w tym temacie.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.

    ![Obszar roboczy funkcje globalne](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    Zostanie otwarta strona **Funkcje fakturowania elektronicznego**.

    ![Strona Funkcje fakturowania elektronicznego](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Dodaj pochodną funkcję globalizacji

Nową funkcję globalizacji można dodać, wywodząc ją z istniejącej funkcji, która została opublikowana lub udostępniona.

1. Wybierz opcję **Import**, aby otworzyć stronę **Importuj funkcję z repozytorium globalnego**.

    ![Funkcja importu ze strony Repozytorium globalne](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. Wybierz opcję **Synchronizuj**, aby uzyskać najnowsze funkcje.

    Zsynchronizowana lista zawiera dostępne funkcje, ponieważ zostały one opublikowane przez firmę Microsoft lub udostępnione przez innego dostawcę konfiguracji.

    ![Zsynchronizowana lista funkcji](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. Z listy wybierz funkcje do zaimportowania, a następnie wybierz opcję **Importuj**. Po pomyślnym zaimportowaniu wybranych funkcji zostanie wyświetlony komunikat.

    ![Komunikat o pomyślnym importowaniu](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Wybierz opcję **Dodaj**, a następnie w oknie dialogowym rozwijanym wybierz opcję **Na podstawie istniejącej wersji**.
5. Wprowadź nazwę i opis funkcji.
6. Na liście dostępnych funkcji wybierz wersję podstawową tej funkcji, a następnie wybierz opcję **Utwórz funkcję**.

    ![Dodawanie funkcji pochodnej](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    Dodana funkcja jest tworzona i ma stan **Wersja robocza**.

    ![Funkcja pochodna o stanie wersji roboczej](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Przejrzyj składniki funkcji, aby określić, czy aktualizacje są wymagane:

    - Przejrzyj konfiguracje, na wypadek potrzeby dostosowania formatów Raportowania elektronicznego (ER) i ich powiązania ich z mapowaniami formatu dla wersji funkcji.
    - Przejrzyj ustawienia, jeśli chcesz dostosować kartę **Akcje**, kartę **Reguły stosowania** lub **Zmienne** dla wersji funkcji.

8. Na karcie **Wersje** wybierz datę **Obowiązuje od** i wprowadź opis, jeśli pole **Opis** jest puste.
9. Aby zakończyć tę funkcję, wybierz opcję **Zmień stan**. Ukończone funkcje można udostępnić dla określonego środowiska, aby mogły być używane w usługach globalizacji, lub mogą być publikowane w repozytorium globalnym.

> [!NOTE]
> Funkcje, które mają wartość **Stan wersji funkcji** jako **Opublikowano**, mogą być udostępniane organizacjom zewnętrznym.

## <a name="add-a-new-globalization-feature"></a>Dodaj nową funkcję globalizacji

Nową funkcję globalizacji można dodać, tworząc ją od podstaw.

1. Na stronie **Importuj funkcję z repozytorium globalnego** wybierz opcję **Dodaj**, a następnie w oknie dialogowym rozwijanym wybierz opcję **Nowa funkcja**.
2. Wprowadź nazwę i opis funkcji.
3. Wybierz opcję **Utwórz funkcję**.

    ![Dodawanie nowej funkcji](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. Na karcie **Wersje** wybierz datę **Obowiązuje od**, a następnie wybierz opcję **Zmień stan**, aby zakończyć tę funkcję. Ukończone funkcje można udostępnić dla określonego środowiska, aby mogły być używane w usługach globalizacji, lub mogą być publikowane w repozytorium globalnym.

> [!NOTE]
> Funkcje, które mają wartość **Stan wersji funkcji** jako **Opublikowano**, mogą być udostępniane organizacjom zewnętrznym.

## <a name="feature-component-overview"></a>Omówienie składnika funkcji

Funkcje globalizacji mają kilka składników:

- **Wersja** — ten składnik obsługuje zarządzanie cyklem życia funkcji i umożliwia użytkownikom zarządzanie stanem różnych wersji tej funkcji.
- **Konfiguracje** — ten składnik umożliwia użytkownikom zarządzanie, wyświetlanie i edytowanie pokrewnych formatów raportowania elektronicznego i mapowaniem formatów.
- **Konfiguracje** — ten składnik umożliwia użytkownikom usług globalizacji, takich jak usługa fakturowania elektronicznego, zarządzanie konfiguracją odpowiedniej wersji funkcji. Z tego względu system obsługuje elastyczne konstruowanie reguł komunikacji i odpowiedzi.
- **Środowisko** — ten składnik umożliwia użytkownikom usług globalizacji, takich jak usługa faktury elektroniczne, zarządzanie środowiskiem, w którym jest używana konfiguracja wersji funkcji, i udzielanie autoryzacji użytkownikom, którzy będą mieli do niego dostęp.
- **Organizacje** — ten składnik umożliwia użytkownikom udostępnianie tej funkcji organizacjom zewnętrznym.

## <a name="configuring-feature-components"></a>Konfigurowanie składników funkcji

### <a name="version-and-status"></a>Wersja i stan

Ta wersja służy do zarządzania cyklem życia funkcji globalizacji.

Stan można zmienić w polu **Stan** na karcie **Wersja**. Dostępne są następujące stany:

- **Wersja robocza** — Funkcja może być edytowana tylko wtedy, gdy znajduje się w tym stanie.
- **Pełna** — Funkcja i wszystkie powiązane składniki zostały sfinalizowane (ukończone) i nie można ich edytować.
- **Opublikowano** — Funkcja i wszystkie powiązane składniki zostały opublikowane w repozytorium globalnym.
- **Udostępnione** — Funkcja i wszystkie powiązane składniki zostały udostępnione organizacjom zewnętrznym.
- **Włączone** — Funkcja i wszystkie powiązane składniki zostały włączone do użycia w usłudze globalizacji, takiej jak usługa fakturowania elektronicznego.

> [!NOTE]
> Funkcje muszą przechodzić sekwencyjnie przez niektóre z tych stanów. Z tego względu nie każdy stan może być dostępny w każdym etapie cyklu eksploatacji.

### <a name="configurations"></a>Konfiguracje

Dla konfiguracji dostępne są następujące działania:

- **Wyświetlanie** — umożliwia wyświetlenie konfiguracji funkcji, które nie wymagają aktualizacji.
- **Edycja** — umożliwia utworzenie wersji roboczej wybranej konfiguracji, dzięki czemu można edytować format lub mapowanie formatów w Projektancie formatów.
- **Usuwanie** — służy do usuwania wybranej konfiguracji z funkcji.
- **Zmiana podstawy** — umożliwia zmianę podstawy funkcji. Aby uzyskać więcej informacji, zobacz sekcję [Zmiana podstawy pochodnych funkcji globalizacji](#rebase) w następnej części tego tematu.

### <a name="setups"></a>Konfiguracje

Dostępne są następujące akcje dla konfiguracji funkcji:

- **Dodaj** — umożliwia utworzenie nowej konfiguracji funkcji. Ta funkcja może pochodzić z istniejącej konfiguracji funkcji lub utworzona od podstaw.
- **Usuwanie** — umożliwia usunięcie wybranej konfiguracji funkcji.
- **Wyświetlanie** — umożliwia wyświetlenie podstawowej konfiguracji funkcji, w której nie są wymagane żadne zmiany.
- **Edycja** — służy do tworzenia, usuwania i modyfikowania atrybutów trzech głównych składników konfiguracji funkcji:

    - Akcje i ich parametry
    - Reguły zastosowania
    - Zmienne

![Strona ustawień wersji funkcji](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Środowiska

Dla środowisk dostępne są następujące działania:

- **Włącz** — dla wybranej wersji funkcji wybierz opublikowane środowisko i wybierz datę **Obowiązuje od**, która powinna być dostępna. Aby uzyskać więcej informacji, zobacz sekcję [Skonfiguruj środowiska do włączania](#configureenvironment) w następnej części tego tematu.
- **Anuluj** — umożliwia usuwanie środowiska konfiguracji funkcji.

### <a name="organizations"></a>Organizacje

Aby udostępnić funkcję globalizacji w organizacji zewnętrznej, należy wykonać następujące kroki.

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz funkcję i wersję funkcji do udostępnienia.
2. Na karcie **Organizacje** wybierz pozycję **Udostępnij**, a następnie w oknie dialogowym rozwijanym wprowadź nazwę domeny organizacji.
3. Wybierz opcję **Udostępnij**.

    ![Udostępnianie funkcji organizacji](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

Funkcja jest udostępniana wybranej organizacji zewnętrznej i jest dostępna dla tej organizacji w repozytorium globalnym. Stamtąd funkcja może być zaimportowana do instancji organizacji RCS lub Dynamics 365 Finance, żeby mogła zostać użyta.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Zmiana podstawy pochodnych funkcji globalizacji

Możesz zmienić pochodną funkcji globalizacji na nową lub zaktualizowaną podstawową wersję funkcji. W ten sposób można automatycznie zaktualizować zmiany, które nastąpiły w wersji podstawowej. Zaktualizowana wersja podstawowa funkcji jest tworzona przez źródłowego dostawcę konfiguracji i jest następnie publikowana lub udostępniana.

![Zaktualizowana wersja funkcji podstawowej](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Na przykład, aby można było zmienić podstawę pochodnej wersji utworzonej wcześniej funkcji, należy najpierw zaimportować ją z repozytorium globalnego.

1. Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj**.
2. Wybierz opcję **Synchronizuj**, aby uzyskać najnowsze funkcje.
3. Z listy funkcji wybierz funkcje do zaimportowania, a następnie wybierz opcję **Importuj**.

    ![Importowanie najnowszej wersji funkcji](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. Z listy funkcji wybierz funkcję do zmiany podstawy.
5. Na karcie **Wersja** wybierz opcję **Nowa**, aby utworzyć wersję roboczą.

    ![Utworzono nową wersję roboczą](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Wybierz opcję **Zmień podstawę**.
7. W oknie dialogowym **Zmiana podstawy** wybierz najnowszą wersję funkcji, która ma być poddana zmianie podstawy.

    ![Okno dialogowe zmiana podstawy](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Kliknij przycisk **OK**.
9. Przejrzyj składniki funkcji i wprowadź wymagane zmiany.
10. Aby zakończyć zmianę podstawy funkcji, wybierz opcję **Zmień stan**. Po zakończeniu zmiany podstawy można wykonać dodatkowe akcje. Można na przykład opublikować tę funkcję i udostępnić ją do użytku w usługach globalizacji.

    ![Stan funkcji został zaktualizowany na zakończono](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>Konfigurowanie środowisk dla funkcji globalizacji

Użytkownicy usług globalizacji mogą zarządzać środowiskiem, aby skonfigurować funkcję globalizacji i udzielić autoryzacji innym użytkownikom, którzy będą mieli do niej dostęp.

1. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Środowiska** wybierz kafelek **Fakturowanie elektroniczne**.

    ![Obszar roboczy funkcje globalizacji](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Wybierz **Parametry usługi Key Vault**, a następnie wybierz opcję **Nowy**, aby utworzyć klucz tajny Azure Key Vault.
3. Wprowadź nazwę i opis magazynu kluczy, a następnie w polu **Identyfikator URI magazynu kluczy** wprowadź adres URL identyfikujący zasób Key Vault w Azure.
4. Na skróconej karcie **Certyfikaty** wybierz przycisk **Dodaj**, aby dodać certyfikat, i wprowadź nazwę i opis każdego certyfikatu.

    ![Dodano certyfikat](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Wybierz pozycję **Nowy**, aby utworzyć nowe środowisko.
6. Wprowadź nazwę, opis oraz poufny token podpisu dostępu współdzielonego wymagany dla magazynu.
7. Na skróconej karcie **Użytkownicy** wybierz opcję **Nowy**, aby dodać użytkownika, który będzie miał uprawnienia dostępu do tego środowiska.
8. Wprowadź identyfikator użytkownika i adres e-mail użytkownika.
9. Powtórz kroki 7 i 8, aby dodać więcej użytkowników.
10. Wybierz opcję **Publikuj**, aby opublikować środowisko.

    ![Opublikowane środowisko](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
