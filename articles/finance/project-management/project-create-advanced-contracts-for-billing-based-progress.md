---
title: Tworzenie zaawansowanych umów dla rozliczeń na podstawie stanu realizacji
description: W tym temacie opisano sposób tworzenia umów dotyczących projektów, dzięki czemu można generować faktury dla odbiorców na podstawie procentu ukończonej pracy.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282843"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Tworzenie zaawansowanych umów dla rozliczeń na podstawie stanu realizacji
[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia umów dotyczących projektów, dzięki czemu można tworzyć faktury dla odbiorców na podstawie procentu ukończonej pracy. Kwoty faktur są obliczane automatycznie dla kategorii budżetu pracy, który skonfigurowano dla projektu. Informacje o czasach faktur są skonfigurowane podczas negocjowania umowy dotyczącej projektu z odbiorcą.

Użyj tych procedur w tym temacie, aby skonfigurować umowę, skojarzony projektu i reguły fakturowania używane do obliczania kwot faktury dla kategorii budżetu, które należy utworzyć dla projektu.

Po utworzeniu umowy i projektu można utworzyć szczegóły projektu. Na przykład można określić działania i przydzielić pracowników do projektu.

## <a name="example"></a>Przykład

Organizacja jest firmą zajmującą się tworzeniem oprogramowania. Użytkownik godzi się na opracowanie pakietu do księgowania listy płac dla odbiorcy za 20 000 dolarów amerykańskich USD. Organizacja zgadza się wysłać fakturę odbiorcy po ukończeniu określonych procentowo części pracy nad tym projektem. Istnieje możliwość skonfigurowania następujących kategorii projektu dla pracy, dzięki czemu można ich używać w procesie rozliczania:

- Konsultacje
- Projekt
- Instalacja

Należy zdefiniować reguły fakturowania, które obliczą automatycznie kwoty faktury dla procentu pracy projektu dla poszczególnych kategorii.

Menedżer budżetu tworzy budżetu dla kategorii projektu. Wielkość ukończonej już pracy jest obliczana automatycznie jako procent rzeczywistej pracy w porównaniu w wielkością budżetu.

## <a name="prerequisites"></a>Wymagania wstępne

Przed utworzeniem projektu, w którym są używane reguły fakturowania, należy skonfigurować sekwencje numerów dla reguł fakturowania oraz arkusz opłat używany do księgowania rozliczeń w toku.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Ustawienia** \> **Parametry modułu Zarządzanie projektami i ich księgowanie**.
2. Na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** na karcie **Numery kolejne** skonfiguruj sekwencję numerów, która ma być używana podczas tworzenia reguł fakturowania.
3. Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Arkusze** \> **Opłata**.
4. Na stronie **Arkusz opłat** wybierz opcję **Nowy** i wprowadź nazwę arkusza.

## <a name="create-a-contract-for-progress-billings"></a>Konfigurowanie umowy dla fakturowania uwarunkowanego stanem realizacji umowy

Ta procedura umożliwia tworzenie umowy dotyczącej projektu dla projektu o stałej cenie. Tworzysz fakturę za projekt, gdy w projekcie wykonano określoną procentowo część pracy.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Umowy dotyczące projektu**.
2. Na stronie **Umowy dotyczące projektu** wybierz opcję **Nowa**.
3. W wyświetlonym oknie dialogowym **Nowa umowa dotycząca projektu** można ustawić następujące pola:

    - **Imię i nazwisko**
    - **Typ finansowania**
    - **Źródło finansowania**
    - **Waluta sprzedaży** — domyślnie jest to waluta używana w fakturach dla odbiorcy, skojarzona z umową dotyczącą projektu. Możesz jednak zmienić walutę sprzedaży dla wybranej faktury dla odbiorcy.

4. Kliknij przycisk **OK**. Informacje zostaną skopiowane do nagłówka strony **Umowy dotyczące projektu**.
5. Na stronie **Umowy dotyczące projektu** wprowadź pozostałe wymagane informacje dotyczące projektu.

## <a name="create-a-project-for-progress-billings"></a>Konfigurowanie umowy dla fakturowania uwarunkowanego stanem realizacji umowy

Wykonaj te kroki, aby stworzyć projekt oraz podprojekty skojarzone z umową dotyczącą projektu.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Wszystkie projekty**.
2. Na stronie **Wszystkie projekty** wybierz opcję **Nowe**.
3. W oknie dialogowym **Nowy projekt**, w polu **Typ projektu** wybierz opcję **Czas i materiały**.
4. Służy do wybierania grupy projektów. Grupa projektów definiuje informacje o księgowaniu dla projektów przypisanych do grupy.
5. Wybierz opcję **Utwórz projekt**.
6. Po utworzeniu projektu ustaw etap projektu **W toku**.

## <a name="create-a-budget-for-a-project"></a>Tworzenie budżetu dla projektu

Kategorie budżetu są używane celu automatycznego obliczania kwot faktur za wykonaną, procentowo określoną część pracy dla każdej kategorii. Aby utworzyć kategorie budżetu dla kosztów szacowanych, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Wszystkie projekty**.
2. Na stronie **Wszystkie projekty** wybierz odpowiedni projekt i otwórz go.
3. Na stronie **Projekty** w okienku akcji, na karcie **Plan**, w grupie **Budżet** wybierz opcję **Budżet projektu**.
4. Na stronie **Budżet projektu** wprowadź szacowany koszt dla każdej kategorii w projekcie.

## <a name="create-billing-rules-for-progress-billings"></a>Umożliwia tworzenie reguł fakturowania uwarunkowanego stanem realizacji umowy

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Projekty** \> **Umowy dotyczące projektu**.
2. Na stronie **Umowy dotyczące projektu** wybierz opcję i otwórz umowę dotyczącą projektu.
3. Na stronie umowa dotycząca projektu w skróconej karcie **Reguły fakturowania** wybierz pozycję **Dodaj**.
4. Na stronie **Reguła fakturowania** w polu **Typ wiersza** wybierz opcję **Postęp**.
5. Na skróconej karcie **Szczegóły wiersza reguły fakturowania** wprowadź łączną wartość umowy w polu **Wartość umowy**.
6. W polu **Kategoria** wybierz kategorię, aby zaksięgować transakcję opłaty.
7. W polu **Projekt** wybierz projekt lub zadanie, które korzysta z tej reguły rozliczeń.
8. Opcjonalne: Przypisz regułę fakturowania do dodatkowych projektów. Na skróconej karcie **Projekt**, w sekcji **Dostępne projekty** wybierz projekt, a następnie wybierz przycisk strzałka w prawo, aby dodać projekt do sekcji **Wybrane projekty**.
9. Opcjonalne: Oblicz procent kwoty, jaka zostanie potrącona na zaliczki na podatek od płatności z faktury odbiorcy. Na skróconej karcie **Warunki zatrzymywania płatności** wybierz źródło finansowania, a następnie w polu **Procent zatrzymania** wprowadź zatrzymywany procent.
10. Powtórz te kroki w celu utworzenia dodatkowych reguł fakturowania dla umowy dotyczącej projektu.
