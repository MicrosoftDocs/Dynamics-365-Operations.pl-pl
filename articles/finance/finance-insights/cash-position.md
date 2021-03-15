---
title: Stan środków pieniężnych (wersja zapoznawcza)
description: W tym temacie opisano sposób, w jaki funkcja prognozowania przepływów pieniężnych umożliwia prognozowanie stanu środków pieniężnych w określonym czasie. Opisano tu także opcje, które są dostępne do wyświetlania prognoz dla różnych okresów.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 5cf1ac4de07cb6357493a0b2c84f6a6ee591d4bc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990571"
---
# <a name="cash-position-preview"></a>Stan środków pieniężnych (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Stan środków pieniężnych to projekcja przepływu pieniężnego, która jest prognozą na bliski okres. Jest ona oparta na projekcji blankietów kasowych odbiorców, którzy płacą zaległe faktury i zamówienia, a także na rozchodach gotówkowych płaconych dostawcom za faktury zakupu i zamówienia.

Podczas przewidywania płatności odbiorcy system używa prognoz płatności z funkcji przewidywania płatności odbiorcy. Bez przewidywania płatności data płatności jest obliczana na podstawie średniego czasu wymaganego do przekonwertowania faktury odbiorcy na płatność od danego odbiorcy. W przypadku otwartych zamówień odbiorcy system oblicza datę faktury, używając średniej liczby dni dla wierszy zamówienia na odbiorcę do zafakturowania. Następnie używa daty faktury jako danych wejściowych funkcji przewidywania płatności. Funkcja przewidywania płatności odbiorcy oblicza datę płatności dla każdego wiersza zamówienia. 

<*Potrzebny tekst od Jarka lub Dave'a w jaki sposób są konwertowane przewidywania płatności na dzień*> Data płatności zaległych faktur jest przybliżona [*oszacowane*] z prognoz płatności, przez wybranie daty odpowiadającej piątemu percentylowi skumulowanej funkcji rozkładu, która jest uzyskiwana z przewidywanych prawdopodobieństw zasobnika.

Podobne podejście służy do przewidywania płatności dla dostawców. W przypadku każdego dostawcy system oblicza średni czas wymagany do przekonwertowania faktury dostawcy na płatność. Na podstawie liczby dni jest następnie obliczana data płatności. W przypadku otwartych zamówień dostawców system oblicza datę faktury, uwzględniając średnią liczbę dni wymaganą do przekonwertowania wierszy zamówienia na fakturę dla każdego dostawcy. Następnie system datę płatności przy użyciu średniego czasu do przekonwertowania faktury dostawcy na płatność dla poszczególnych dostawców.

Górna sekcja karty **Stan środków pieniężnych** zawiera wykres stanu środków pieniężnych. Ten wykres pokazuje przychody i wypływy gotówkowe oraz ich wpływ na łączne salda płynności. Szczegóły na wykresie stanu środków pieniężnych można wyświetlać w okresach dziennych, tygodniowych, miesięcznych lub kwartalnych. Po wybraniu opcji **Dziennie** można wyświetlić prognozy na następne 21 dni. Po wybraniu opcji **Tygodniowa** można wyświetlić prognozy na następne 20 tygodni. Po wybraniu opcji **Miesięczna** można wyświetlić prognozy na następne 12 miesięcy. Po wybraniu opcji **Kwartalna** można wyświetlić prognozy na następne 12 kwartałów. Jeśli wymagane jest dodatkowe miejsce na ekranie, można ukryć wykres, aby wyświetlić zawartość na karcie **Stan środków pieniężnych**.

Dolna sekcja karty **Stan środków pieniężnych** zawiera szczegółowe informacje dotyczące stanu, przepływu pieniężnego, prognozowanych płatności oraz konta bankowego.

- Informacje zawarte w siatce **Szczegóły stanu** są przedstawione w trzech sekcjach: lista kont płynności, lista dokumentów tworzących przychody gotówkowe oraz lista dokumentów tworzących rozchody gotówkowe. W siatce są także wyświetlane salda stanu środków pieniężnych. Dla pierwszego wyświetlanego okresu saldo dla kont płynności jest saldem otwarcia. W kolejnych okresach salda kont płynności są obliczane na podstawie dodania przychodów gotówkowych i odejmowania rozchodów gotówkowych z poprzednich okresów. Aby wyświetlić szczegóły transakcji, które składają się na saldo, należy wybrać łącze **Saldo**.
- W siatce **Przepływ pieniężny** są wyświetlane przychody gotówkowe, wypływy środków pieniężnych zagregowane według okresów oraz ich wpływ na salda kont płynności. Dla pierwszego okresu saldo dla kont płynności jest saldem otwarcia. W kolejnych okresach salda kont płynności są obliczane na podstawie dodania przychodów gotówkowych i odejmowania rozchodów gotówkowych z poprzednich okresów.
- W siatce **Prognozowane saldo bankowe** widoczne są oczekiwane rozchody pieniężne i ich wpływ na konta płynności.
- W siatce **Konto bankowe** jest wyświetlany wpływ oczekiwanych przychodów i rozchodów gotówkowych na saldo bankowe.

Aby zapisać i edytować stan środków pieniężnych, należy utworzyć migawkę. Aby uzyskać więcej informacji na temat pracy z migawkami, zobacz [Omówienie migawek](payment-snapshots.md).

#### <a name="privacy-notice"></a>Klauzula prywatności
Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]