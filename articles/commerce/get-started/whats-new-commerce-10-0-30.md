---
title: Wersja zapoznawcza Dynamics 365 Commerce 10.0.30 (listopad 2022)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w Microsoft Dynamics 365 Commerce 10.0.30.
author: josaw1
ms.date: 12/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: a449c7eff21c059555f9659ea932705858d26275
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831755"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>Wersja zapoznawcza Dynamics 365 Commerce 10.0.30 (listopad 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Commerce w wersji zapoznawczej w wersji 10.0.30. Ta wersja ma numer kompilacji 10.0.1362 i jest dostępna w następującym harmonogramie:

- **Wersja zapoznawcza:** wrzesień 2022
- **Ogólna dostępność wydania (samodzielna aktualizacja):** październik 2022 r.
- **Ogólna dostępność wydania (samoaktualizacja):** Listopad 2022

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten artykuł, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---------|------------------|----------------|--------------| 
| Obsługa klienta   | Czat w witrynie handlu elektronicznego przy użyciu bota Power Virtual Agents. | Ta funkcja spowoduje, że użytkownicy witryny handlu elektronicznego będą mieć możliwość używania bota czatu Power Virtual Agents w żądaniach pomocy technicznej. | Włączone przez administratora/twórców dla użytkowników końcowych |
| Szczegółowe informacje  |  Przesyłaj dane operacyjne punktu sprzedaży do swojego konta Application Insights. | [Dzienniki dostępu w Application Insights](../dev-itpro/operational-insights.md#enable-diagnostic-events-in-application-insights)   |  Zgody profesjonalisty/dewelopera IT   |
|  Płatności  | Obsługa zamówień PayPal poza 29-dniowym okresem autoryzacji. | Maksymalny okres autoryzacji dla usługi PayPal to 29 dni, po upływie którego musi zostać wygenerowany nowy identyfikator autoryzacji i zamówienia. Jako alternatywę, system PayPal oferuje opcję, w której zamówienie PayPal może być odwołaniem do zamówienia ogólnego, umożliwiając wiele autoryzacji i przechwytywanie dla tego samego identyfikatora zamówienia zamiast generowania nowej autoryzacji i identyfikatora zamówienia po 29 dniach). | Podczas konfigurowania łącznika płatności PayPal w programie Commerce Headquarters dodano pole **OrderIntent** i może ono mieć dwie wartości:<p><p>- **Autoryzuj** — ta konfiguracja jest domyślna (jeśli pole jest puste, opcja **Autoryzuj** działa jako domyślna). Konfigurowanie usługi **OrderIntent** do **Autoryzuj** koreluje wartość **processing_instruction** usługi PayPal **NO_INSTRUCTION**. Zamówienie zostanie autoryzowane przy użyciu usługi PayPal, a autoryzacji nie można zmodyfikować, jeśli jest używana ta wartość.<p>- **Zapisz** — jeśli ustawienie **OrderIntent** ma wartość **Zapisz**, skoreluje to wartość właściwości PayPal **processing_instruction** wartości **ORDER_SAVED_EXPLICITLY**. Gdy będzie używana ta wartość, odwołania do zamówień zostaną zapisane w usłudze PayPal.  |
| Logowanie do punktu sprzedaży  | [Włącz samoobsługowe możliwości diagnozy przy logowanie w punkcie sprzedaży](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Ta funkcja udostępnia samoobsługowe funkcje diagnostyki w punkcie sprzedaży i centrali Commerce Headquarters, aby ułatwić pracownikom etatowym i menedżerom szybkie identyfikowanie i rozwiązywanie głównych przyczyn problemów z logowaniem się do punktu sprzedaży.<p><p>- komunikaty o błędzie wyświetlane na ekranie logowania do punktu sprzedaży zostały poprawione, aby zostały podane konkretne informacje na temat powodu błędu, które mogą pomóc pracownikom sklepu, używającym aplikacji, w zrozumieniu, co poszło nie tak, dzięki czemu mogą wykonać niezbędne akcje w celu rozwiązania problemu.<p>- funkcja **logowania testowego** jest dostępna na stronie **Pracownicy** w programie Commerce headquarters, dzięki czemu kierownicy sklepów, którzy skonfigurują urządzenia w punkcie sprzedaży, mogą symulować logowanie do punktu sprzedaży. W przypadku awarii logowania ta funkcja udostępnia przewodniki dotyczące rozwiązywania problemów, dzięki czemu menedżerowie mogą sprawdzać odpowiednie konfiguracje, poprawiać problemy i sprawdzać poprawność poprawek.  | Domyślnie włączona |


## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

W systemie Dynamics 365 Finance 10.0.30 są dostępne aktualizacje platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.30 aplikacji finansowych i operacyjnych](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.30, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.](/dynamics365-release-plan/2022wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-features"></a>Usunięte i wycofane funkcje

Artykuł [Usunięte lub wycofane funkcje w Dynamics 365 Commerce](removed-deprecated-features-commerce.md) opisuje funkcje, które zostały usunięte lub przestarzałe dla handlu.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
