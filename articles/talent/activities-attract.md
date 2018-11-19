---
title: "Działania w procesach"
description: "Ten temat zawiera informacje o różnych typach działań, których można używać w procesie rekrutacji."
author: 
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: ccd9e2d0ff1f7fb6825c6823936b4013b3054f5d
ms.contentlocale: pl-pl
ms.lasthandoff: 10/22/2018

---

# <a name="activities-in-the-hiring-processes"></a>Działania w procesach rekrutacji

[!include[banner](../includes/banner.md)]

Działania można dodawać jako część procesu rekrutacji w programie Microsoft Dynamics 365 for Talent Attract. Działania można dodawać do szablonu procesu albo bezpośrednio do procesu rekrutacji na funkcję. Podczas definiowania funkcji wybiera się szablon procesu i wtedy działania uwzględnione w szablonie są stosowane do funkcji. Jeśli szablon nie zostanie wybrany, będzie używany szablon domyślny. Proces rekrutacji można również modyfikować w funkcji po zastosowaniu szablonu.

> [!NOTE] 
> Szablony procesów są dostępne po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

## <a name="prospect-activity"></a>Działanie Prospekt

Działanie Prospekt kontroluje, czy do funkcji można dodawać prospektów. Domyślnie można dodać prospektów do funkcji. Aby wyłączyć działanie Prospekt, ustaw w opcji **Włącz prospektów** wartość **Wyłączone**. Gdy działanie Prospekt jest włączone, menedżerowie zatrudniający mogą dodawać i przeglądać prospekty, a karta **Prospekt** jest wyświetlana w ustawieniach funkcji.

## <a name="application-activity"></a>Działanie Zgłoszenie

Działanie Zgłoszenie jest wymagane w szablonie procesu rekrutacji. Aby wysyłać wiadomości e-mail kandydatom w reakcji na przesłanie przez nich zgłoszeń lub dodanie ich do etapu Zgłoszenie, ustaw w opcji **Wyślij wiadomość e-mail do kandydata** wartość **Włączone**.

## <a name="scheduler-activity"></a>Działanie Harmonogram

Działanie Harmonogram jest opcjonalne. To działanie ma dwa składniki: Dostępność kandydata i Harmonogram. Składnik Dostępność kandydata umożliwia wysyłanie wiadomości e-mail w celu sprawdzenia dostępności kandydata. Składnik Harmonogram umożliwia planowanie rozmów kwalifikacyjnych z udziałem kandydata i zespołu rekrutacyjnego. W działaniu Harmonogram można skonfigurować następujące opcje: **Zażądaj dostępności kandydata**, **Spotkanie online** i **Wyślij wiadomość e-mail do kandydata**.

- Aby wysłać wiadomości e-mail do kandydatów z pytaniem o ich dostępność, ustaw w opcji **Zażądaj dostępności kandydata** wartość **Włączone**. Jeśli ustawisz tę opcję na **Wyłączone**, ten krok nie będzie wyświetlany w procesie rekrutacji na funkcję.
- Aby użyć transmisji strumieniowej na żywo lub zorganizować połączenie konferencyjne w programie Skype dla firm, ustaw w polu **Spotkanie online** wartość **Skype dla firm**. Wtedy poprawne łącze **Dołącz do spotkania w aplikacji Skype** zostanie dodane do zaproszenia na rozmowę kwalifikacyjną wysyłanego osobom przeprowadzającym rozmowy kwalifikacyjne.
- Aby wysłać wiadomości e-mail do kandydatów w celu sfinalizowania harmonogramu, ustaw w opcji **Wyślij wiadomość e-mail do kandydata** wartość **Włączone**. Jeśli ustawisz tę opcję na **Wyłączone**, kandydaci otrzymają harmonogram rozmów kwalifikacyjnych tylko wtedy, gdy się zalogują do portalu kandydata.

## <a name="feedback-activity"></a>Działanie Opinia

Działanie Opinia jest opcjonalne. Umożliwia ono wprowadzanie rekomendacji dotyczących kandydata przez uczestników rozmowy kwalifikacyjnej. Osoby te mogą także wpisywać wszelkie komentarze, jakie mają. Po włączeniu opcji **Dziedzicz współtwórców opinii z zespołu rekrutacyjnego** osoba rekrutująca, menedżer zatrudniający i osoby przeprowadzające rozmowy kwalifikacyjne są automatycznie dodawane do działania Opinia. Organizacje mogą również zezwalać osobom przeprowadzającym rozmowy kwalifikacyjne na przeglądanie opinii innych osób, zanim prześlą swoje własne opinie. Organizacje mogą także pozwalać osobom przeprowadzającym rozmowy kwalifikacyjne na edytowanie już przesłanych opinii.

## <a name="interview-activity"></a>Działanie Rozmowa kwalifikacyjna

Działanie Rozmowa kwalifikacyjna jest opcjonalne. To działanie ma trzy składniki: Dostępność kandydata, Harmonogram i Opinia. Składnik Dostępność kandydata umożliwia wysyłanie wiadomości e-mail w celu sprawdzenia dostępności kandydata. Składnik Harmonogram umożliwia planowanie rozmów kwalifikacyjnych z udziałem kandydata i zespołu rekrutacyjnego. W działaniu Harmonogram można skonfigurować następujące opcje: **Zażądaj dostępności kandydata**, **Spotkanie online** i **Wyślij wiadomość e-mail do kandydata**.

- Aby wysłać wiadomości e-mail do kandydatów z pytaniem o ich dostępność, ustaw w opcji **Zażądaj dostępności kandydata** wartość **Włączone**. Jeśli ustawisz tę opcję na **Wyłączone**, ten krok nie będzie wyświetlany w procesie rekrutacji na funkcję.
- Aby użyć transmisji strumieniowej na żywo lub zorganizować połączenie konferencyjne w programie Skype dla firm, ustaw w polu **Spotkanie online** wartość **Skype dla firm**. Wtedy poprawne łącze **Dołącz do spotkania w aplikacji Skype** zostanie dodane do zaproszenia na rozmowę kwalifikacyjną.
- Aby wysłać wiadomości e-mail do kandydatów w celu sfinalizowania harmonogramu, ustaw w opcji **Wyślij wiadomość e-mail do kandydata** wartość **Włączone**. Jeśli ustawisz tę opcję na **Wyłączone**, kandydaci otrzymają harmonogram rozmów kwalifikacyjnych tylko wtedy, gdy się zalogują do portalu kandydata.

Składnik Opinia umożliwia osobom wprowadzanie rekomendacji dotyczących kandydata. Osoby te mogą także wpisywać wszelkie komentarze, jakie mają. Po włączeniu opcji **Dziedzicz współtwórców opinii z zespołu rekrutacyjnego** osoba rekrutująca, menedżer zatrudniający i osoby przeprowadzające rozmowy kwalifikacyjne są automatycznie dodawane do składnika Opinia. Organizacje mogą również zezwalać osobom przeprowadzającym rozmowy kwalifikacyjne na przeglądanie opinii innych osób, zanim prześlą swoje własne opinie. Organizacje mogą także pozwalać osobom przeprowadzającym rozmowy kwalifikacyjne na edytowanie już przesłanych opinii.

## <a name="powerapps-activity"></a>Działanie PowerApps

Działanie PowerApps pozwala osadzić aplikację usługi Microsoft PowerApps w procesie rekrutacji. Aplikacja może być wymagana w przypadku wszystkich kandydatów, tylko wewnętrznych kandydatów lub tylko zewnętrznych kandydatów albo w ogóle nie być wymagana. Jeśli aplikacja jest oznaczona jako wymagana, należy wykonać wszystkie przewidziane w niej czynności, zanim będzie można przejść do następnego etapu. Jeśli aplikacja nie jest oznaczona jako wymagana, ma charakter opcjonalny i można przejść do następnego etapu nawet jeśli aplikacja nie zostanie użyta.

Aby zapisać działanie PowerApps w procesie rekrutacji, należy wprowadzić identyfikator usługi PowerApps. Aby znaleźć identyfikator usługi PowerApps, przejdź do strony [PowerApps](https://web.powerapps.com), wybierz opcję **Aplikacje**, a następnie wybierz opcję **Szczegóły**.

W przypadku wybrania opcji **Zezwalaj na dodawanie uczestników do tego działania** można dodawać kolejnych współautorów do aplikacji używającej działania PowerApps. Na przykład organizacja utworzyła aplikację usługi PowerApps, która jest biblioteką pytań zadawanych w rozmowach kwalifikacyjnych osobom aplikującym na funkcje techniczne. Organizacja szuka teraz nowego programisty i dodała działanie PowerApps do procesu rekrutacji na funkcję Programista. Jeśli opcja **Zezwalaj na dodawanie uczestników do tego działania** jest zaznaczona, osoba rekrutująca lub menedżer zatrudniający, który przegląda zgłoszenia kandydatów na funkcję Programista, może dodać więcej osób do działania PowerApps. Osoby te mogą następnie wyświetlać aplikację zawierającą pytania do rozmowy kwalifikacyjnej.

> [!NOTE]
> Działanie PowerApps jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

## <a name="youtube-activity"></a>Działanie YouTube

Działanie YouTube umożliwia udostępnienie filmu z serwisu YouTube w ramach procesu rekrutacji. Aby zapisać działanie YouTube w procesie rekrutacji, musisz podać adres URL do filmu na YouTube. Podobnie jak w przypadku działania PowerApps, możesz pozwolić na dodawanie uczestników do działania. W przypadku wybrania opcji **Pokaż tylko kandydatowi** film będzie widoczny tylko dla kandydatów. Nie będzie wyświetlany w procesie rekrutacji w aplikacji Attract.

> [!NOTE]
> Działanie YouTube jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

## <a name="web-content-activity"></a>Działanie Treści internetowe

Działanie Treści internetowe pozwala osadzać treści z Internetu w procesie rekrutacji. Aby zapisać działanie Treści internetowe w procesie rekrutacji, musisz podać adres URL do treści. Podobnie jak w przypadku działań PowerApps i YouTube, możesz pozwolić na dodawanie uczestników do działania. W przypadku wybrania opcji **Pokaż tylko kandydatowi** materiał będzie widoczny tylko dla kandydatów. Nie będzie wyświetlany w procesie rekrutacji w aplikacji Attract. Można wybrać rozmiar, w takim będzie wyświetlany materiał.

> [!NOTE]
> Działanie Treści internetowe jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

## <a name="microsoft-forms-activity"></a>Działanie Microsoft Forms

Działanie Microsoft Forms pozwala osadzić formularz usługi Microsoft Forms w procesie rekrutacji. Usługa Microsoft Forms umożliwia tworzenie testów, ankiet i sond. Aby zapisać działanie Microsoft Forms w procesie rekrutacji, musisz podać adres URL formularza. Podobnie jak w przypadku działań PowerApps, YouTube i Treści internetowe, możesz pozwolić na dodawanie uczestników do działania. W przypadku wybrania opcji **Pokaż tylko kandydatowi** formularz będzie widoczny tylko dla kandydatów. Nie będzie wyświetlany w procesie rekrutacji w aplikacji Attract.

W usłudze Microsoft Forms autorzy mogą zmieniać swoje ustawienia, aby umożliwić użytkownikom spoza organizacji odpowiadanie w ankietach i testach. W takim przypadku użytkownicy przesyłają odpowiedzi anonimowo. Jeśli chcesz zobaczyć, kto wypełnił daną ankietę lub test, możesz określić wymóg, aby respondenci podawali swoje imiona i nazwiska w ramach ankiety lub testu.

> [!NOTE]
> Działanie Microsoft Forms jest dostępne tylko po zainstalowaniu dodatku kompleksowej obsługi rekrutacji.

