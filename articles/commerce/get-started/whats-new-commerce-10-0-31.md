---
title: Podgląd Dynamics 365 Commerce 10.0.31 (luty 2023 r.)
description: W tym artykule opisano nowe oraz zmienione funkcje dostępne w Microsoft Dynamics 365 Commerce 10.0.31.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: ed4325095163415d05a56128cb1f0334440fe0e5
ms.sourcegitcommit: c364f50ea0ad50bac5c30724b6ce301d9574b653
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2022
ms.locfileid: "9787534"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>Podgląd Dynamics 365 Commerce 10.0.31 (luty 2023 r.)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Commerce w wersji zapoznawczej w wersji 10.0.31. Ta wersja ma numer kompilacji 10.0.1406 i jest dostępna w następującym harmonogramie:

- **Wersja zapoznawcza wydania:** Październik 2022
- **Ogólna dostępność wydania (samoaktualizacja):** styczeń 2023
- **Ogólna dostępność wydania (samoaktualizacja):** luty 2023

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Możemy zaktualizować ten artykuł, aby uwzględnić cechy, które zostały dodane do kompilacji po opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Kody błędów | Rozwiązanie Commerce wprowadziło standardowe odwołania do błędów, które można uwzględniać w błędach realizacji transakcji kanału online, wyświetlanych kupującym w trybie online.| [Kody błędów modułu wyewidencjonowania](../checkout-module-error-codes.md)  | Domyślnie włączona |
| Płatności | [Włączanie Apple Pay z Dynamics 365 Payment Connector dla Adyen](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | Korzystając z obsługiwanych urządzeń lub przeglądarki, klienci handlu elektronicznego mogą używać Apple Pay w koszyku i na stronach wyewidencjonowania. | Zgoda dewelopera |
| Płatności  |  Dzięki usługom Commerce można ograniczyć sposób interakcji użytkowników z tokenami płatności cyklicznych w interfejsie użytkownika programu Commerce headquarters. Formularze płatności, takie jak strona **Zamówienia sprzedaży dla centrum obsługi**, nie wyświetlają już wcześniej wykorzystanego przez klienta cyklicznego tokenu płatności, który ma być wykorzystywany w nowej transakcji. Podczas przetwarzania płatności za nową transakcję, tylko określona „karta w pliku” wejściowa na ekran płatności odbiorcy w portalu Commerce **Płatności klienta** lub za zgodą klienta w przypadku płatności przy użyciu zamówienia sprzedaży będzie przedstawiana użytkownikom działu obsługi lub centrali Commerce headquarters. | [Limit użycia tokenu płatności](../dev-itpro/limit-token-usage.md)  |  Zarządzanie funkcjami<p>*Ogranicz użycie tokenu płatności do kontekstu zamówienia*  |
| Punkt sprzedaży | [Tworzenie zamówień zakupu w punkcie sprzedaży](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  Poprawione przychodzące operacje magazynowe w aplikacji punktu sprzedaży (POS) umożliwiają użytkownikom tworzenie, edytowanie i potwierdzanie żądań zamówienia zakupu. |  Zarządzanie funkcjami<p>*Możliwość tworzenia żądania zamówienia zakupu w punkcie sprzedaży*   |
| Dostępne są dodatkowe języki | Dostępne są cztery dodatkowe języki | Na liście języków preferowanych dostępne są cztery nowe języki do wyboru przez użytkownika: Koreański, Portugalski ( Portugalia), Wietnamski i Chiński (Tradycyjny). Aby wybrać tę opcję, przejdź do **Opcje użytkownika \> Preferencje \> Preferencje dotyczące języka i kraju/regionu**. | Zlokalizowane preferencje |  



## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji Finanse i Działania

Microsoft Dynamics 365 Commerce 10.0.31 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.31 aplikacji finansowych i operacyjnych (luty 2023)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.31, należy zalogować się do Microsoft Dynamics Lifecycle Services i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 2 wersji z 2022 r.](/dynamics365-release-plan/2022wave2/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-commerce-features"></a>Usunięte i wycofane funkcje Commerce

Artykuł [Usunięte lub wycofane funkcje w Dynamics 365 Commerce](removed-deprecated-features-commerce.md) opisuje funkcje, które zostały usunięte lub przestarzałe dla handlu.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 miesięcy przed usunięciem.


W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
