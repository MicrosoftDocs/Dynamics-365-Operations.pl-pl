---
title: Wgląd w płatności od odbiorców (wersja zapoznawcza)
description: W tym artykule opisano funkcjonalność wglądu w płatności, która pomaga zrozumieć typowe praktyki płatnicze konkretnych odbiorców. Funkcja może również pomóc w identyfikowaniu okoliczności, które uzasadniają rozpoczęcie procesów windykacji wcześniej, niż normalnie rozważałaby organizacja.
author: ShivamPandey-msft
ms.date: 11/06/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 54655d2b1cfb4b11f32842d4c3cff2f4d8e97ef5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856807"
---
# <a name="customer-payment-insights-preview"></a>Wgląd w płatności od odbiorców (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym artykule opisano funkcjonalność wglądu w płatności, która pomaga zrozumieć typowe praktyki płatnicze konkretnych odbiorców. Funkcja może również pomóc w identyfikowaniu okoliczności, które uzasadniają rozpoczęcie procesów windykacji wcześniej, niż normalnie rozważałaby organizacja. 

## <a name="overview"></a>Omówienie

Często trudno przewidzieć, kiedy odbiorcy zapłacą faktury. Ten brakujący wgląd w nieścisły wpływ na mniej dokładne prognozy przepływów pieniężnych, procesy windykacji, które zaczynają zbyt późno, oraz zamówienia, które są zwalniane do odbiorców, którzy mogą domyślnie księgować. Moduł Wgląd w płatności od odbiorców (wersja zapoznawcza) pomaga organizacjom przewidzieć, kiedy zostanie zapłata faktura wystawiona odbiorcy. Te informacje mogą pomóc organizacjom w tworzeniu strategii windykacji, które zwiększają prawdopodobieństwo otrzymania zapłaty w terminie. 

## <a name="predictions"></a>Prognozy

Przewidywania płatności umożliwiają organizacjom ulepszanie procesów biznesowych dzięki łatwemu identyfikowaniu faktur, które prawdopodobnie zostaną spłacone, oraz podjęcia odpowiednich środków, które zwiększają szanse na zapłatę na czas.

Za pomocą modelu nauki maszyn, który wykorzystuje historyczne faktury, płatności i dane odbiorców, szczegółowe informacje o płatnościach (Podgląd) — dokładniejsze przewidywania w przypadku, gdy odbiorca zapłaci zaległą fakturę.

Dla każdej otwartej faktury narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) może przewidywać trzy prawdopodobieństwa zapłaty:

-   Prawdopodobieństwo dokonania płatności w czasie 
-   Prawdopodobieństwo dokonania płatności opóźnionej
-   Prawdopodobieństwo dokonania płatności bardzo opóźnionej

Aby ułatwić organizacjom zrozumienie łącznej kwoty płatności, której mogą oczekiwać od odbiorcy w jednym z trzech przedziałów (Na czas, Opóźnione i Bardzo opóźnione), moduł Wgląd w płatności od odbiorców (wersja zapoznawcza) przekazuje także zagregowany widok oczekiwanych płatności.

[![Zagregowany widok prognoz płatności.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Ponadto do każdej faktury jest przypisywane prawdopodobieństwo płatności na czas. Jeśli prawdopodobieństwo płatności na czas jest mniejsze niż 50%, faktury są znakowane czerwoną kółkiem, aby wskazać, że te faktury mogą wymagać windykacji. 

[![Prawdopodobieństwo listy płatności.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Szczegóły płatności odbiorcy (wersja zapoznawcza) zawierają również informacje kontekstowe w celu wyjaśnienia przewidywania, takie jak najlepsze czynniki wpływające na prognozę, bieżący stan działalności gospodarczej z odbiorcą oraz szczegółowe informacje dotyczące historycznej płatności odbiorcy działa. W wielu firmach proces windykacji był aktywnym działaniem; Proces windykacji nie rozpoczyna się do terminu wymagalności faktur. 

Dzięki usłudze wgląd do płatności odbiorcy (wersja zapoznawcza) organizacje mogą być bardziej aktywne w sprawie windykacji. Nie muszą oni już czekać na pozyskanie transakcji z powodu rozpoczęcia procesu zbierania danych. Zamiast tego mogą one używać funkcji przewidywania płatności, aby określić, czy aktywne kolekcje będą poprawiać prawdopodobieństwo zapłaty na czas. Funkcja przewidywania płatności zapewnia także firmom informacje potrzebne do potwierdzenia rozpoczęcia procesu zbierania danych w pierwszej kolejności.

## <a name="methodology"></a>Metodologia

Opracowywanie i wdrażanie rozwiązania AI jest trudne. Potrzeba zespołu specjalistów ds. nauki o danych, ekspertów merytorycznych (SME) i inżynierów, którzy wkładają mnóstwo pracy w sformułowanie, opracowanie, wdrażanie i bieżące utrzymywanie użytecznego rozwiązania AI. Ułatwia to wdrażanie i korzystanie z rozwiązań AI w Finance. Firma Microsoft udostępnia wstępnie używane rozwiązania AI w Finansach, które są tworzone na podstawie modułu Microsoft AI Builder. Użytkownik końcowy z jednym kliknięciem przycisku może wdrożyć rozwiązanie AI i zacząć korzystanie z zalet inteligentnych prognoz. Jeśli organizacja nie jest zadowolony z dokładnością prognoz, użytkownik zaawansowany za pomocą jednego kliknięcia może wejść w środowisko rozszerzenia AI Builder, a następnie zaznaczyć lub usunąć zaznaczenie pól używanych do generowania prognoz. Jak są gotowe mogą one pociągać i publikować zmiany, a nowy model przeszkolony jest automatycznie pobierany na potrzeby prognoz w Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Jak otrzymać aplikację Wgląd w płatności od odbiorców (wersja zapoznawcza)

Jeśli interesuje Cię wypróbowanie narzędzia [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com), wyślij wiadomość e-mail do zespołu odpowiedzialnego za wersje zapoznawcze funkcji wglądu w parametry finansowe.

## <a name="privacy-notice"></a>Klauzula prywatności

Ponadto wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations (2) nie są objęte umową dotyczącą poziomu usług dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
