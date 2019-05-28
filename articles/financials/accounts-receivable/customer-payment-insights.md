---
title: Wgląd w płatności od odbiorców (wersja zapoznawcza)
description: W tym temacie opisano, jak narzędzie Wgląd w płatności od odbiorców może pomóc przewidzieć, kiedy faktura zostanie zapłacona, oraz pomaga organizacjom tworzyć strategie optymalizacji zwiększające prawdopodobieństwo otrzymania zapłaty w terminie.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566262"
---
# <a name="customer-payment-insights-preview"></a>Wgląd w płatności od odbiorców (wersja zapoznawcza)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Ta funkcja stanowi część wydania kierowanego i jest dostępna tylko dla użytkowników, którzy zarejestrowali się na prywatną wersję zapoznawczą. Ta funkcja zostanie umieszczona w jednym z przyszłych wydań, które będzie ogólnie dostępne.

# <a name="overview"></a>Przegląd

Organizacje często mają problemy z przewidzeniem, kiedy odbiorcy zapłacą faktury. Ten brak informacji może prowadzić do niedokładnych prognoz przepływów pieniężnych, nieefektywnych procesów windykacji oraz niebezpieczeństwa realizowania zamówień dla klientów, którzy stanowią ryzyko kredytowe. Narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) wykorzystuje mechanizmy uczenia maszynowego do przewidywania, kiedy faktura zostanie zapłacona. Oferuje także strategie optymalizacji, które można dostosować w celu zmaksymalizowania prawdopodobieństwo terminowego otrzymania zapłaty od odbiorców.

## <a name="predictions"></a>Prognozy

Mechanizm prognoz płatności umożliwia organizacjom usprawnienie procesów biznesowych przez:

-   Łatwe identyfikowanie faktur, po których można oczekiwać, że zostaną zapłacone z opóźnieniem.
-   Podejmowanie właściwych działań w celu zwiększenia szans na otrzymanie zapłaty w terminie.

Narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) wykorzystuje mechanizmy uczenia maszynowego do przewidywania, kiedy faktura zostanie zapłacona. Narzędzie wykorzystuje historyczne dane faktur, płatności i odbiorców w celu zbudowania modelu uczenia maszynowego, który służy do przewidywania, kiedy faktura zostanie zapłacona.

Dla każdej otwartej faktury narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) przewiduje trzy prawdopodobieństwa zapłaty:

-  Prawdopodobieństwo zapłaty na czas (w terminie wymagalności faktury).
-  Prawdopodobieństwo zapłaty w ciągu 30 dni od daty wymagalności faktury.
-  Prawdopodobieństwo zapłaty po 30 dniach od daty wymagalności faktury.

Prawdopodobieństwo zapłaty można oglądać w sekcji prognozowania.

[![Prognozy płatności](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

Każdej fakturze jest również przypisywane największe prawdopodobieństwo zapłaty przy użyciu jednego z trzech zdefiniowanych powyżej scenariuszy przewidywanego prawdopodobieństwa zapłaty. Zwycięskim scenariuszem jest scenariusz o najwyższym prawdopodobieństwie zapłaty.


Na przykład załóżmy, że dla faktury prognoza pokazuje 71-procentowe prawdopodobieństwo zapłaty na czas, 13-procentowe prawdopodobieństwo zapłaty w ciągu 30 dni od daty wymagalności oraz 16-procentowe prawdopodobieństwo zapłaty ponad 30 dni od daty wymagalności. Najwyższe prawdopodobieństwo pokazuje, że faktura znajdzie się w scenariuszu zapłaty na czas, dlatego zostanie oznaczona w ten sposób.

[![Prognozy płatności](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Strategie optymalizacji

Oprócz prognoz płatności narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) może wykorzystywać strategie optymalizacji w celu zwiększenia szans na otrzymanie zapłaty w terminie. Pozwala to organizacji przeprowadzić analizę wariantową poprzez umożliwienie użytkownikom dostosowania parametrów faktur i odbiorców, a następnie porównanie powstałego wpływu na prawdopodobieństwo otrzymania płatności za faktury na czas.

Na przykład organizacja może chcieć ocenić wpływ aktualizacji rabatu gotówkowego w fakturach na prawdopodobieństwo otrzymania płatności w terminie. Gdy faktury zostaną zoptymalizowane pod kątem używania nowego rabatu, użytkownicy mogą sprawdzić wpływ zastosowania rabatu na prawdopodobieństwo otrzymywania płatności za te faktury na czas. Jeśli koszt zastosowania rabatu jest minimalny w stosunku do korzyści polegającej na otrzymaniu płatności na czas, organizacja może postanowić stosować wybrany rabat do wszystkich przyszłych otwartych zamówień.

> [!NOTE] 
> Obecnie w narzędziu Wgląd w płatności od odbiorców (wersja zapoznawcza) jedną dostępną strategią optymalizacji są rabaty.

[![Zoptymalizowane prognozy](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Jak otrzymać aplikację Wgląd w płatności od odbiorców (wersja zapoznawcza)

Jeśli interesuje Cię wypróbowanie narzędzia Wgląd w płatności od odbiorców (wersja zapoznawcza), wyślij wiadomość e-mail do [zespołu odpowiedzialnego za wersje zapoznawcze funkcji wglądu w parametry finansowe](mailto:fiap@microsoft.com). 

## <a name="privacy-statement"></a>Zasady zachowania poufności informacji

Dane odbiorców w wersjach zapoznawczych narzędzi są przechowywane w Stanach Zjednoczonych. Ponadto wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 for Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.
