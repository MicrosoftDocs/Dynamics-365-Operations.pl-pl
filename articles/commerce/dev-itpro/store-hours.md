---
title: Tworzenie i aktualizacja godzin w sklepie
description: W tym artykule opisano sposób tworzenia i aktualizowania godzin sklepu w programie Commerce Headquarters.
author: josaw1
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 99d2f06be959e00656901c6ca8fc79fac32a3a6f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884372"
---
# <a name="create-and-update-store-hours"></a>Tworzenie i aktualizacja godzin w sklepie

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a>Omówienie

Z jednego miejsca Detaliści mogą tworzyć, obsługiwać i zarządzać godzinami przechowywania różnych sklepów w regionach geograficznych. Godziny sklepu mogą być następnie wyświetlane w terminalach punkt sprzedaży (POS). W ten sposób kasjerzy mogą współużytkować godziny w sklepie z odbiorcami, a lepsza pomoc Shoppers osób zainteresowanych zapasami w innych sklepach. Godziny sklepu mogą być również drukowane na paragonach, na wypadek, gdyby odbiorcy mogli później powrócić do sklepu.

Wiele godzin sklepu można skonfigurować w różnych kanałach. Te kanały obejmują sklepy fizyczne, biura obsługi, urządzenia przenośne oraz witryny handlu elektronicznego

Jeśli odbiorca ma zamówienie pobrania dla innego sklepu, kasjer może wybrać daty, kiedy pobranie będzie dostępne w tym sklepie. Wyszukiwanie w sklepie będzie zawierać odwołanie do dat i godzin przechowywania. Kasjer może wybrać datę i lokalizację, a także wydrukować przyjęcie do pobrania zawierające godziny sklepowe.

Ta funkcja jest dostępna w Microsoft Dynamics 365 Retail wersjach 8.1.2 i nowszych.

## <a name="configure-store-hours"></a>Konfiguruj godziny pracy sklepu

Aby skonfigurować godziny pracy sklepu, wykonaj następujące kroki.

1. Przejdź do **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Godziny otwarcia sklepu**.
2. Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon godzin pracy. Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku.
3. W oknie dialogowym **Dodaj zakres** określ zakres dat, godziny sklepu oraz wszelkie wymagane święta.

    - Jeśli godziny sklepu nie zmieniają się, należy wybrać opcję **Nigdy nie zakończone** w polu **Data zakończenia**.
    - Jeśli godziny w sklepie dotyczą określonego miesiąca, tygodnia lub dnia, należy określić odpowiednie daty w polach **Data początkowa** i **Data końcowa**.

    > [!NOTE]
    > Można utworzyć wiele szablonów mających nakładające się daty rozpoczęcia i zakończenia. Można więc na przykład zdefiniować godziny sklepu w różnych strefach czasowych.

    ![Dodaj zakres okna dialogowego.](../dev-itpro/media/Storehours1.png "Dodaj zakres okna dialogowego")

4. Szablonem godzin sklepu należy skojarzyć z magazynami, w których będzie używany. W oknie dialogowym **Wybieranie węzłów organizacji** wybierz sklepy, regiony i organizacje, z którymi szablon ma być skojarzony.

    - Z każdym sklepem można skojarzyć tylko jeden szablon godzin sklepu.
    - Za pomocą przycisków strzałek wybierz sklepy, regiony lub organizacje Kalendarz będzie dostępny dla sklepów lub grup sklepów i będzie widoczny w punkcie sprzedaży dla celów referencyjnych.

    ![Wybierz okienko dialogowe węzły organizacji.](../dev-itpro/media/Storehours2.png "Wybierz okienko dialogowe węzły organizacji")

5. Na stronie **harmonogramdystrybucji** uruchom zadania **1070** i **1090**, aby udostępnić godziny sklepu w punkcie sprzedaży.

## <a name="add-store-hours-to-printed-receipts"></a>Dodawanie godzin sklepu do przyjęć drukowanych

Wykonaj poniższe kroki, aby dodać godziny sklepu do wydrukowanych przyjęć w punkcie sprzedaży.

1. Otwórz projektanta formatu paragonu.
2. Zaznacz **Stopkę** w lewym dolnym rogu.
3. Przeciągnij element **Godziny pracy sklepu** z lewego okienka do stopki w dolnej części szablonu paragonu.
4. W razie konieczności można edytować domyślną etykietę w **Godziny pracy sklepu**.
5. Zapisz paragon i zamknij projektanta formatu paragonu.
6. Na stronie **harmonogram dystrybucji** ruchom zadania **1070** and **1090**.
7. Zaloguj się w kasie POS.
8. Zakończ sprzedaż i wybierz opcję drukowania paragonu.

W przyjęciu w punkcie sprzedaży zostaną uwzględnione godziny sklepu. Jeśli w szablonie uwzględniono dni wolne od pracy, zostaną one wyświetlone na paragonie.

![Przykład paragonu.](../dev-itpro/media/Storehours3.png "Przykład paragonu")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]