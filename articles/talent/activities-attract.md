---
title: Działania w procesach
description: Ten temat zawiera informacje o różnych typach działań, których można używać w procesie rekrutacji.
author: hasrivas
manager: AnnBe
ms.date: 04/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c975b95e4195c795ec4c816b1f3a50461715feea
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/12/2019
ms.locfileid: "989921"
---
# <a name="activities-in-the-hiring-processes"></a>Działania w procesach rekrutacji

[!include[banner](../includes/banner.md)]

Działania można dodawać jako część procesu rekrutacji w programie Microsoft Dynamics 365 for Talent: Attract. Działania można dodawać do szablonu procesu albo bezpośrednio do procesu rekrutacji na funkcję. Podczas definiowania funkcji wybiera się szablon procesu i wtedy działania uwzględnione w szablonie są stosowane do funkcji. Jeśli szablon nie zostanie wybrany, będzie używany szablon domyślny. Proces rekrutacji można również modyfikować w funkcji po zastosowaniu szablonu.

> [!NOTE] 
> Szablony procesów są dostępne po zainstalowaniu dodatku kompleksowej obsługi rekrutacji. Aby uzyskać dodatkowe informacje, zobacz [Funkcje dodatku kompleksowej obsługi rekrutacji w aplikacji Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Działanie Prospekt

Działanie Prospekt kontroluje, czy do funkcji można dodawać prospektów. Domyślnie można dodać prospektów do funkcji. Aby wyłączyć działanie Prospekt, ustaw w opcji **Włącz prospektów** wartość **Wyłączone**. Gdy działanie Prospekt jest włączone, menedżerowie zatrudniający mogą dodawać i przeglądać prospekty, a karta **Prospekt** jest wyświetlana w ustawieniach funkcji.

## <a name="application-activity"></a>Działanie Zgłoszenie

Działanie Zgłoszenie jest wymagane w szablonie procesu rekrutacji. Aby wysyłać wiadomości e-mail kandydatom w reakcji na przesłanie przez nich zgłoszeń lub dodanie ich do etapu Zgłoszenie, ustaw w opcji **Wyślij wiadomość e-mail do kandydata** wartość **Włączone**.

## <a name="interview-schedule-and-feedback-activity"></a>Działanie planowania rozmów kwalifikacyjnych i informacji zwrotnych

To działanie ma trzy składniki: Żądanie dostępność kandydata, Harmonogram i Opinia. Użyj działania rozmowy kwalifikacyjnej w szablonie zadania, jeśli chcesz uwzględnić żądanie dostępności kandydata, harmonogramu i informacje zwrotnych w ramach procesu zamiast używać ich osobno w trakcie zatrudnienia. Aby uzyskać więcej informacji, zobacz [Planowanie rozmów kwalifikacyjnych i informacji zwrotnych](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>Działanie PowerApps

Działanie PowerApps pozwala osadzić aplikację usługi Microsoft PowerApps w procesie rekrutacji. Aplikacja może być wymagana w przypadku wszystkich kandydatów, tylko wewnętrznych kandydatów lub tylko zewnętrznych kandydatów albo w ogóle nie być wymagana. Jeśli aplikacja jest oznaczona jako wymagana, należy wykonać wszystkie przewidziane w niej czynności, zanim będzie można przejść do następnego etapu. Aby pole **JobApplicationStatus** zostało uznane za zakończone, musi być ustawione jako **Gotowe**. To pole znajduje się w jednostce JobApplicationActivity, więc aplikacja PowerApps będzie musiała zaktualizować to pole, zanim będzie można przejść do kolejnego etapu. Jeśli aplikacja nie jest oznaczona jako wymagana, ma charakter opcjonalny i można przejść do następnego etapu nawet jeśli aplikacja nie zostanie użyta.

Aby zapisać działanie PowerApps w procesie rekrutacji, należy wprowadzić identyfikator usługi PowerApps. Aby znaleźć identyfikator usługi PowerApps, przejdź do strony [PowerApps](https://web.powerapps.com), wybierz opcję **Aplikacje**, a następnie wybierz opcję **Szczegóły**.

Domyślnie działania usługi PowerApps jest dostępne dla Menedżera zatrudnienia, Osoby rekrutującej i ich przedstawicieli. W przypadku wybrania opcji **Zezwalaj na dodawanie uczestników do tego działania** można dodawać kolejnych uczestników z zespołu rekrutacyjnego do aplikacji używającej działania PowerApps. Na przykład organizacja utworzyła aplikację usługi PowerApps, która jest biblioteką pytań zadawanych w rozmowach kwalifikacyjnych osobom aplikującym na funkcje techniczne. Organizacja szuka teraz nowego programisty i dodała działanie PowerApps do procesu rekrutacji na funkcję Programista. Jeśli opcja **Zezwalaj na dodawanie uczestników do tego działania** jest zaznaczona, osoba rekrutująca lub menedżer zatrudniający, który przegląda zgłoszenia kandydatów na funkcję Programista, może dodać osoby przeprowadzające rozmowy kwalifikacyjne do działania PowerApps. Osoby te mogą następnie wyświetlać aplikację zawierającą pytania do rozmowy kwalifikacyjnej.

> [!NOTE]
> Działanie PowerApps jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji. Aby uzyskać dodatkowe informacje, zobacz [Funkcje dodatku kompleksowej obsługi rekrutacji w aplikacji Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>Działanie YouTube

Działanie YouTube umożliwia udostępnienie filmu z serwisu YouTube w ramach procesu rekrutacji. Aby zapisać działanie YouTube w procesie rekrutacji, musisz podać adres URL do filmu na YouTube. Istnieje możliwość wyświetlania zawartości **zespołowi rekrutacyjnemu**, **tylko wewnętrznym kandydatom**, **tylko zewnętrznym kandydatom** lub **wszystkim kandydatom**. Podobnie jak w przypadku działania PowerApps, możesz pozwolić na dodawanie uczestników zespołu rekrutacyjnego do działania. Jeśli zostanie wybrana opcja pokazywania zawartości kandydatom, to wideo jest wyświetlane tylko po uruchomieniu przez kandydata, a nie w procesie zatrudniania.

> [!NOTE]
> Działanie YouTube jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji. Aby uzyskać dodatkowe informacje, zobacz [Funkcje dodatku kompleksowej obsługi rekrutacji w aplikacji Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Działanie Treści internetowe

Działanie Treści internetowe pozwala osadzać treści z Internetu w procesie rekrutacji. Aby zapisać działanie Treści internetowe w procesie rekrutacji, musisz podać adres URL do treści. Istnieje możliwość wyświetlania zawartości **zespołowi rekrutacyjnemu**, **tylko wewnętrznym kandydatom**, **tylko zewnętrznym kandydatom** lub **wszystkim kandydatom**. Podobnie jak w przypadku działania PowerApps i YouTube, możesz pozwolić na dodawanie uczestników zespołu rekrutacyjnego do działania. Jeśli zostanie wybrana opcja pokazywania zawartości kandydatom, ta zawartość sieciowa jest wyświetlana tylko po uruchomieniu przez kandydata, a nie w procesie zatrudniania. Można wybrać rozmiar, w takim będzie wyświetlany materiał.

> [!NOTE]
> Działanie Treści internetowe jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji. Aby uzyskać dodatkowe informacje, zobacz [Funkcje dodatku kompleksowej obsługi rekrutacji w aplikacji Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Działanie Microsoft Forms

Działanie Microsoft Forms pozwala osadzić działanie usługi Microsoft Forms w procesie rekrutacji. Usługa Microsoft Forms umożliwia tworzenie testów, ankiet i sond. Aby zapisać działanie Microsoft Forms w procesie rekrutacji, musisz podać adres URL formularza. Istnieje możliwość wyświetlania zawartości **zespołowi rekrutacyjnemu**, **tylko wewnętrznym kandydatom**, **tylko zewnętrznym kandydatom** lub **wszystkim kandydatom**. Podobnie jak w przypadku działania PowerApps, YouTube i zawartości sieciowej możesz pozwolić na dodawanie uczestników zespołu rekrutacyjnego do działania. Jeśli zostanie wybrana opcja pokazywania zawartości kandydatom, ten formularz jest wyświetlany tylko po uruchomieniu przez kandydata, a nie w procesie zatrudniania.

W usłudze Microsoft Forms autorzy mogą zmieniać swoje ustawienia, aby umożliwić użytkownikom spoza organizacji odpowiadanie w ankietach i testach. W takim przypadku użytkownicy przesyłają odpowiedzi anonimowo. Jeśli chcesz zobaczyć, kto wypełnił daną ankietę lub test, możesz określić wymóg, aby respondenci podawali swoje imiona i nazwiska w ramach ankiety lub testu.

> [!NOTE]
> Działanie Microsoft Forms jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji. Aby uzyskać dodatkowe informacje, zobacz [Funkcje dodatku kompleksowej obsługi rekrutacji w aplikacji Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Działanie oferty

Ten szablon procesu zatrudnienia wymaga działania Oferta. Aby użyć oferty zintegrowanej aplikacji zarządzania, należy ustawić **Uruchom aplikację Offer Management podczas przygotowywania oferty** jako **Wł**. Jeśli to ustawienie jest wyłączone, kandydat, to nie pojawi się w aplikacji oferty, więc trzeba będzie ręcznie śledzić aktualizacje do oferty kandydata. Aby określić, czy menedżerowie zatrudniający mogą przygotować oferty dla kandydata w aplikacji Oferta, należy ustawić **Menedżerowie zatrudniający mogą przygotować ofertę** jako **Wł**. Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk, można zdecydować, czy chcesz przygotować wiele ofert dla tego samego numeru stanowiska. Jeśli chcesz zezwolić tylko na jedną ofertę na stanowisko na zadanie, ustaw **Zezwalaj na wielokrotne używanie stanowisk w funkcji** jako **Wył**.

> [!NOTE]
> Zintegrowana aplikacja Offer Management jest dostępna tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji. Aby uzyskać dodatkowe informacje, zobacz [Funkcje dodatku kompleksowej obsługi rekrutacji w aplikacji Attract](./attract-comprehensive-hiring.md).


