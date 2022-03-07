---
title: Prognozy płatności odbiorcy (wersja zapoznawcza)
description: W tym temacie opisano funkcjonalność prognoz płatności, która może pomóc w lepszym zrozumieniu typowych praktyk płatniczych odbiorcy. Ta funkcja może również pomóc w identyfikowaniu okoliczności, które powinny spowodować rozpoczęcie procesów windykacji wcześniej, niż normalnie rozważałaby organizacja.
author: ShivamPandey-msft
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 4151b56b8b385e29d3926dc7e245728158cbcd34
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5898019"
---
# <a name="customer-payment-predictions-preview"></a>Prognozy płatności odbiorcy (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano funkcjonalność prognoz płatności, która może pomóc w lepszym zrozumieniu typowych praktyk płatniczych odbiorcy. Ta funkcja może również pomóc w identyfikowaniu okoliczności, które powinny spowodować rozpoczęcie procesów windykacji wcześniej, niż normalnie rozważałaby organizacja.

## <a name="overview"></a>Omówienie

Organizacje często mają problemy z przewidzeniem, kiedy odbiorcy zapłacą faktury. Ten brak szczegółowych informacji może powodować następujące problemy:

- Mniej dokładne prognozy przepływów pieniężnych
- Procesy windykacji, które zaczynają zbyt późno
- Zamówienia zwolnione do odbiorców, którzy mogą nie uregulować płatności

Moduł Prognozy płatności odbiorcy (wersja zapoznawcza) pomaga organizacjom przewidzieć, kiedy zostanie zapłata faktura wystawiona odbiorcy. Dzięki temu mogą oni tworzyć strategie windykacji, które pomagają zwiększyć prawdopodobieństwo, że zapłata wpłynie w terminie.

## <a name="predictions"></a>Prognozy

Prognozy płatności pozwalają organizacjom ulepszać procesy biznesowe poprzez łatwiejsze identyfikowanie faktur, które prawdopodobnie zostaną zapłacone z opóźnieniem. Organizacja może wykorzystywać te informacje do podejmowania działań, które zwiększają szanse, że pieniądze wpłyną w terminie.

Funkcja Prognozy płatności odbiorcy używa modelu uczenia maszynowego do dokładniejszego przewidywania, kiedy odbiorca zapłaci zaległą fakturę. Ten model uczenia maszynowego zawiera historyczne dane faktur, płatności i odbiorców.

Dla każdej otwartej faktury funkcja przypisuje trzy prawdopodobieństwa płatności:

- Prawdopodobieństwo, że płatność zostanie dokonana na czas
- Prawdopodobieństwo, że płatność zostanie dokonana z opóźnieniem
- Prawdopodobieństwo, że płatność zostanie dokonana z dużym opóźnieniem

Funkcja umożliwia także wyświetlanie zagregowanego widoku oczekiwanych płatności.

[![Zagregowany widok prognoz płatności](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Do każdej faktury jest przypisywane prawdopodobieństwo płatności na czas. Faktury mające prawdopodobieństwo płatności na czas jest mniejsze niż 50% są znakowane czerwoną kółkiem, aby wskazać, że mogą wymagać uwagi agenta ds. windykacji.

[![Prawdopodobieństwo listy płatności](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Funkcja Prognozy płatności odbiorcy dostarcza również informacji kontekstowych objaśniających przewidywanie. Informacje te obejmują najważniejsze czynniki, które miały wpływ na prognozę, obecny stan współpracy biznesowej z odbiorcą oraz szczegóły dotyczące historycznego regulowania płatności przez odbiorcę.

W wielu firmach proces windykacji jest działaniem reaktywnym. Innymi słowy rozpoczyna się dopiero wtedy, gdy faktury stają się wymagalne. Moduł Prognozy płatności odbiorcy pomaga organizacjom stosować bardziej proaktywny proces windykacji. Nie muszą już one czekać z rozpoczęciem procesu windykacji do momentu, aż zapłata za transakcję stanie się wymagalna. Zamiast tego mogą one używać funkcji prognoz płatności, aby określić, czy proaktywna windykacja zwiększy prawdopodobieństwo otrzymania zapłaty na czas.

## <a name="methodology"></a>Metodologia

W przeszłości zazwyczaj trudno było opracować i wdrożyć rozwiązanie wykorzystujące sztuczną inteligencję (AI). Proces wymagał zespołu specjalistów ds. nauki o danych, ekspertów merytorycznych (SME) i inżynierów, którzy pracowali często w nadgodzinach, aby sformułować, opracować, wdrożyć i na bieżąco utrzymywać użyteczne rozwiązanie AI. Moduł Prognozy płatności odbiorcy ułatwia wdrażanie i używanie rozwiązania AI w rozwiązaniu Microsoft Dynamics 365 Finance. Microsoft udostępnia gotowe rozwiązania AI oparte na aplikacji Microsoft AI Builder. Dzięki temu użytkownicy mogą wdrożyć rozwiązanie AI jednym kliknięciem myszy i szybko zacząć korzystać z zalet inteligentnych prognoz. Jeśli organizacja nie jest zadowolona z dokładności prognoz, użytkownik zaawansowany (ponownie za pomocą jednego kliknięcia) może wejść w środowisko rozszerzenia AI Builder, a następnie zaznaczyć lub usunąć zaznaczenie pól używanych do generowania prognoz. Gdy wszystko będzie gotowe, można „wytrenować” model i opublikować zmiany. Nowo wytrenowany model będzie automatycznie wybierany na potrzeby generowania prognoz w rozwiązaniu Dynamics 365 Finance.

## <a name="release-details"></a>Szczegóły zwolnienia

Publiczna wersja zapoznawcza Finance Insights jest dostępna do wypróbowania we wdrożeniach w Stanach Zjednoczonych Ameryki, Europie i Zjednoczonym Królestwie. Firma Microsoft stopniowo dodaje obsługę kolejnych regionów.

Funkcje publicznej wersji zapoznawczej powinny być włączone tylko w środowiskach piaskownicy warstwy 2. Konfiguracja i modele AI utworzone w środowisku piaskownicy mogą nie być migrowane do środowiska produkcyjnego. Aby uzyskać więcej informacji, zobacz [Uzupełniające warunki użytkowania wersji zapoznawczych Microsoft Dynamics 365](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).

## <a name="privacy-notice"></a>Klauzula prywatności

Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]