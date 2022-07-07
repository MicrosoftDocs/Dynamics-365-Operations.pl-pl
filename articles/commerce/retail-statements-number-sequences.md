---
title: Konfigurowanie sekwencji identyfikatorów dla zestawień sprzedaży detalicznej
description: W tym artykule opisano, jak skonfigurować sekwencje numerów, które są wymagane dla zestawień detalicznych w Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 917d7b7a905a822ca3b1e074055fe0cd4af5555b
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027193"
---
# <a name="set-up-number-sequences-for-retail-statements"></a>Konfigurowanie sekwencji identyfikatorów dla zestawień sprzedaży detalicznej

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak skonfigurować sekwencje numerów, które są wymagane dla zestawień detalicznych w Microsoft Dynamics 365 Commerce.

W Dynamics 365 Commerce używane są dwa rodzaje zestawień detalicznych: 

- **Wyciągi transakcyjne** są przeznaczone do tworzenia i publikowania z dużą częstotliwością. Służą one do księgowania wszystkich transakcji niefinansowych w sklepie do centrali Dynamics 365 Commerce. 
- **Sprawozdania finansowe** mają być tworzone i księgowane jeden raz na dzień biznesowy. Zawierają one tylko zamknięte zmiany ze sklepów detalicznych, które zostały przesłane do centrali Commerce poprzez p-job.

## <a name="configure-a-number-sequence-for-statement-posting"></a>Skonfiguruj sekwencję numerów dla księgowania wyciągów

Po zakończeniu konfiguracji sklepu detalicznego, w centrali Commerce musisz skonfigurować unikalną sekwencję numerów, która będzie używana w zestawieniach podczas procesu tworzenia zestawienia.

Aby skonfigurować sekwencję numerów dla księgowania wyciągów w centrali Commerce, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Numery kolejne \> Numery kolejne**.
1. Wybierz pozycję **Nowy \> Sekwencja liczbowa**, aby utworzyć nową sekwencje numerów.
1. Na skróconej karcie **Identyfikacja**, w polu **Kod sekwencji numerów** wprowadź kod sekwencji numerów.
1. W polu **Nazwa sekwencji numerów** wpisz nazwę.
1. Na skróconej karcie **Parametry Scope** w polu **Scope** wybierz pozycję **Jednostka operacyjna**.
1. W polu **Jednostka operacyjna** wybierz sklep, dla którego będzie używana sekwencja numerów.
1. W zakładce **Segmenty** zdefiniuj segmenty.
1. Na skróconej karcie **Odniesienia** ustaw pole **Obszar** na **Sklep sieci sprzedaży**.
1. Ustaw w polu **Odniesienie** wartość **Numer oświadczenia**, a następnie wybierz **OK**.

    ![Skrócone karty Identyfikacja, Parametry zakresu, Segmenty i Odniesienia na stronie Sekwencje numerów.](media/retail-statements-num-seq-setup-01.png)

1. W zakładce **Ogólne**, w sekcji **Przydział numerów** zaktualizuj pola **Najmniejszy** i **Największy** tak, aby odpowiadały długości **segmentu alfanumerycznego**, który zdefiniowałeś w zakładce **Segmenty**.
1. Na skróconej karcie **Wydajność** zalecamy ustawienie opcji **Prealokacja** na **Tak**, a pola **Ilość liczb** na **25**.

    ![Skrócone karty Ogólne i Wydajność na stronie sekwencji numerów.](media/retail-statements-num-seq-setup-02.png)

1. Na pasku akcji wybierz **Zapisz**, aby zapisać zmiany i zamknąć stronę.
