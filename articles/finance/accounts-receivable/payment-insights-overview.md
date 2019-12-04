---
title: Wgląd w płatności od odbiorców (wersja zapoznawcza)
description: W tym temacie opisano możliwości wglądu do płatności, które ułatwiają zrozumienie typowych praktyk płatności poszczególnych odbiorców i umożliwiają identyfikowanie okoliczności, które uzasadniają inicjowanie procesów zbierania danych wcześniej niż w przypadku wykonania innych czynności.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774026"
---
# <a name="customer-payment-insights-preview"></a>Wgląd w płatności od odbiorców (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano możliwości wglądu do płatności, które ułatwiają zrozumienie typowych praktyk płatności poszczególnych odbiorców i umożliwiają identyfikowanie okoliczności, które uzasadniają inicjowanie procesów zbierania danych wcześniej niż w przypadku wykonania innych czynności. 

## <a name="overview"></a>Omówienie

Organizacje często mają problemy z przewidzeniem, kiedy odbiorcy zapłacą faktury. Ten brakujący wgląd w nieścisły wpływ na mniej dokładne prognozy przepływów pieniężnych, procesy windykacji, które zaczynają zbyt późno, oraz zamówienia, które są zwalniane do odbiorców, którzy mogą domyślnie księgować. Narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) organizacji może pomóc przewidzieć, kiedy faktura od odbiorcy zostanie zapłacona, oraz pomaga organizacjom tworzyć strategie kolekcji zwiększające prawdopodobieństwo otrzymania zapłaty w terminie. 

## <a name="predictions"></a>Prognozy

Przewidywania płatności umożliwiają organizacjom ulepszanie procesów biznesowych dzięki łatwemu identyfikowaniu faktur, które prawdopodobnie zostaną spłacone, oraz podjęcia odpowiednich środków, które zwiększają szanse na zapłatę na czas.

Za pomocą modelu nauki maszyn, który wykorzystuje historyczne faktury, płatności i dane odbiorców, szczegółowe informacje o płatnościach (Podgląd) — dokładniejsze przewidywania w przypadku, gdy odbiorca zapłaci zaległą fakturę.

Dla każdej otwartej faktury narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) przewiduje trzy prawdopodobieństwa zapłaty:

-   Prawdopodobieństwo dokonania płatności w czasie 
-   Prawdopodobieństwo dokonania płatności opóźnionej
-   Prawdopodobieństwo dokonania płatności bardzo opóźnionej

Aby ułatwić organizacjom zrozumienie łącznej kwoty płatności, które mogą oczekiwać od odbiorcy w jednym z trzech przedziałów, na czas, późny i bardzo późno, informacje o płatnościach (wersja zapoznawcza) umożliwiają także Zagregowany widok oczekiwanych płatności.

[![Zagregowany widok prognoz płatności](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Ponadto do każdej faktury jest przypisywane prawdopodobieństwo płatności na czas. Jeśli prawdopodobieństwo płatności na czas jest mniejsze niż 50%, faktury są znakowane czerwoną kółkiem, aby wskazać, że te faktury mogą wymagać windykacji. 

[![Prawdopodobieństwo listy płatności](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Szczegóły płatności odbiorcy (wersja zapoznawcza) zawierają również informacje kontekstowe w celu wyjaśnienia przewidywania, takie jak najlepsze czynniki wpływające na prognozę, bieżący stan działalności gospodarczej z odbiorcą oraz szczegółowe informacje dotyczące historycznej płatności odbiorcy działa. W wielu firmach proces windykacji był aktywnym działaniem; Proces windykacji nie rozpoczyna się do terminu wymagalności faktur. 

Dzięki usłudze wgląd do płatności odbiorcy (wersja zapoznawcza) organizacje mogą być bardziej aktywne w sprawie windykacji. Nie muszą oni już czekać na pozyskanie transakcji z powodu rozpoczęcia procesu zbierania danych. Zamiast tego mogą one używać funkcji przewidywania płatności, aby określić, czy aktywne kolekcje będą poprawiać prawdopodobieństwo zapłaty na czas. Funkcja przewidywania płatności zapewnia także firmom informacje potrzebne do potwierdzenia rozpoczęcia procesu zbierania danych w pierwszej kolejności.

## <a name="methodology"></a>Metodologia

Opracowywanie i wdrażanie rozwiązania AI jest trudne. Pobiera zespół danych naukowców, ekspertów i inżynierów, którzy pracują przez dłuższy czas do formułowania, opracowywania, wdrażania i obsługiwania dostępnego rozwiązania AI. Ułatwia to wdrażanie i korzystanie z rozwiązań AI w Finance. Firma Microsoft udostępnia wstępnie używane rozwiązania AI w Finance, które są tworzone na podstawie modułu Microsoft AI Builder. Użytkownik końcowy z jednym kliknięciem przycisku może wdrożyć rozwiązanie AI i zacząć korzystanie z zalet inteligentnych prognoz. Jeśli organizacja nie jest zadowolony z dokładnością prognoz, użytkownik zaawansowany za pomocą jednego kliknięcia może wejść w środowisko rozszerzenia AI Builder, a następnie zaznaczyć lub usunąć zaznaczenie pól używanych do generowania prognoz. Jak są gotowe mogą one pociągać i publikować zmiany, a nowy model przeszkolony jest automatycznie pobierany na potrzeby prognoz w Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Jak otrzymać aplikację Wgląd w płatności od odbiorców (wersja zapoznawcza)

Jeśli interesuje Cię wypróbowanie narzędzia [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com), wyślij wiadomość e-mail do zespołu odpowiedzialnego za wersje zapoznawcze funkcji wglądu w parametry finansowe.

## <a name="privacy-notice"></a>Klauzula prywatności

Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


