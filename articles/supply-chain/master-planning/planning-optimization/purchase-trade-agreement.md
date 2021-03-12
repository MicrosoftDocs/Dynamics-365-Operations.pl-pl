---
title: Planowanie główne za pomocą umów handlowych zakupu
description: W tym temacie opisano sposób, w jaki Optymalizacja planowania może znaleźć dostawcę i/lub czas realizacji zamówienia planowanego na podstawie najlepszej ceny lub czasu realizacji, który znajduje się w umowach handlowych zakupu.
author: ChristianRytt
manager: tfehr
ms.date: 06/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: e060f20b65153a7bbe70996e6ff4c3930468348a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992252"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Planowanie główne za pomocą umów handlowych zakupu

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób, w jaki Optymalizacja planowania może znaleźć dostawcę i/lub czas realizacji zamówienia planowanego na podstawie najlepszej ceny lub czasu realizacji, który znajduje się we wszystkich umowach handlowych zakupu, które zostały określone dla danego produktu.

## <a name="turn-on-the-purchase-trade-agreements-for-planning-optimization-feature"></a>Włącz funkcję Umów handlowych zakupu na potrzeby Optymalizacji planowania

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Planowanie główne*
- **Nazwa funkcji:** *Umowy handlowe zakupu na potrzeby Optymalizacji planowania*

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Przygotowanie systemu do oceny umów handlowych zakupu podczas planowania głównego

Aby skonfigurować system do stosowania Optymalizacji planowania, która ocenia umowy handlowe zakupu, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Parametry planowania głównego**. Na karcie **Zamówienia planowane** w sekcji **Dostawca** określ następujące wartości:

    - **Znajdź umowę handlową** — ustawienie tej opcji na wartość **Tak** powoduje uwzględnienie umów handlowych zakupu w planowaniu głównym.
    - **Kryterium wyszukiwania** — umożliwia wybór współczynnika, dla którego mają być przydzielane priorytety dla poszczególnych umów handlowych zakupu: **Minimalny czas realizacji** lub **Najniższa cena jednostkowa**.

1. Przejdź do **Zaopatrzenie i sourcing \> Konfiguracja \> Ceny i rabaty \> Aktywuj cenę/rabat** i upewnij się, że opcja **Dostawcy** jest ustawiona na wartość **Tak**.
1. Przejdź do **Zarządzanie informacjami o produktach \> Konfiguracja \> Grupy wymiarów i wariantów \> Grupy wymiarów magazynowania**, a następnie wybierz grupę wymiarów magazynowania, która dotyczy produktów, dla których planowanie główne powinno oceniać umowy handlowe zakupu. Upewnij się, że dla każdego odpowiedniego wymiaru magazynowania w tej grupie jest zaznaczone pole wyboru w kolumnie **Dla cen zakupu**. Powtórz ten krok dla każdej odpowiedniej grupy wymiarów magazynowania.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Przygotowanie wydanego produktu do oceny umów handlowych zakupu podczas planowania głównego

Po przygotowaniu systemu zgodnie z opisem w poprzedniej sekcji należy wykonać poniższe kroki, aby upewnić się, że każdy produkt, który ma być używany z tą funkcją, jest poprawnie skonfigurowany.

1. Otwórz **Zarządzanie informacjami o produktach \> Produkty \> Wydane produkty** i otwórz docelowy produkt.
1. Na skróconej karcie **Zakup** upewnij się, że w polu **Dostawca** nie jest przypisany żaden dostawca.
1. W okienku akcji na karcie **Plan** w grupie **Zapotrzebowanie** wybierz **Zapotrzebowanie na towar**, aby otworzyć stronę **Zapotrzebowanie na towar** dla wybranego produktu. Sprawdź następujące ustawienia:

    - Na karcie **Ogólne** można skonfigurować zastąpienia dostawców. Jeśli Optymalizacja planowania ma używać umów handlowych zakupu w celu wybrania dostawcy, należy wyczyścić pole wyboru **Zastosuj określone ustawienie**.
    - Na karcie **Czas realizacji** można skonfigurować zastąpienia w czasie realizacji. Jeśli Optymalizacja planowania ma używać umów handlowych zakupu w celu wybrania czasów realizacji, należy zapobiec zamianom zastąpienia czasu realizacji. Należy wyczyścić pole wyboru dla każdego typu czasu realizacji, który ma zostać wybrany przy użyciu umów handlowych zakupu (**Zakup**, **Produkcja** i/lub **Przeniesienie**).

1. Zamknij stronę **Zapotrzebowanie na towar**, aby powrócić do strony szczegółów wybranego produktu.
1. W okienku akcji na karcie **Plan** w grupie **Prognozy** wybierz opcję **Prognoza dostaw**, aby otworzyć stronę **Prognoza dostaw**. Upewnij się, że żaden wiersz wyświetlany w tym miejscu nie zawiera wartości w kolumnie **Konto dostawcy**.
1. Zamknij stronę **Prognoza dostaw**, aby powrócić do strony szczegółów wybranego produktu.
1. W okienku akcji, na karcie **Zakup** w grupie **Umowy handlowe** wybierz **Wyświetl umowy handlowe**. Upewnij się, że wszystkie odpowiednie umowy handlowe zakupu są wymienione na liście. Upewnij się również, że opcja **Ignoruj czas realizacji** jest ustawiona na wartość **Nie** dla każdej umowy, w Optymalizacja planowania ma użyć czasu realizacji określonego dla danej umowy.
1. W okienku akcji na karcie **Plan** w grupie **Ustawienia zamówień** wybierz **Ustawienia domyślne zamówień**, aby otworzyć stronę **Ustawienia domyślne zamówień** dla wybranego produktu. Na skróconej karcie **Zamówienia zakupu** zobacz pole **Czas realizacji zakupu**. Jeśli nie zdefiniowano zastąpienia czasu realizacji zapotrzebowania na towary, Optymalizacja planowania będzie używała tej wartości w przypadku wybrania umów handlowych, w których opcja **Ignoruj czas realizacji** jest ustawiona na **Tak**. Dlatego należy dostosować tę wartość w wymagany sposób.
1. Powtórz tę procedurę dla każdego odpowiedniego produktu.

> [!NOTE]
> Waluta w wierszu umowy handlowej zakupu musi być zgodna z walutą wybranego dostawcy. Planowanie główne będzie zawierać tylko informacje z wierszy umowy handlowej zakupu, których waluta pasuje do waluty dostawcy.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Przykłady zastosowania Optymalizacji planowania w odnalezieniu dostawcy i czasu realizacji

Poniższa tabela zawiera przykłady, które pokazują, jak różne ustawienia wydanego produktu i skojarzone z nim umowy handlowe zakupu wpływają na wartości znalezione dla wynikowego planowanego zamówienia zakupu. **Pogrubione** wartości w dwóch skrajnych kolumnach po prawej stronie to wartości wybrane przez Optymalizację planowania. Wartości **_pogrubione i zapisane kursywą_* _ w innych kolumnach to ustawienia, które wywołały wartości dla każdego wiersza.

| Zwolniony produkt: Dostawca | Domyślne ustawienia zamówień: Czas realizacji | Zapotrzebowanie na towar: Zastąp dostawcę | Zapotrzebowanie na towar: Zastąp czas realizacji | Umowa handlowa: Dostawca | Umowa handlowa: Czas realizacji | Umowa handlowa: Ignoruj czas realizacji | Wynikowy dostawca | Wynikowy czas realizacji |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| _*_US001_*_ | _*_1_*_ | Nr | Nr | US003 | 3 | Nr | _ *US001** | **1** |
| US001 | 1 | **_Tak: US002_* _ | _*_Tak: 2_*_ | US003 | 3 | Nr | _ *US002** | **2** |
| *(Puste)* | 1 | Nr | Nr | ***US003** _ | _*_3_*_ | Nr | _ *US003** | **3** |
| *(Puste)* | ***1** _ | Nr | Nr | _*_US003_*_ | 3 | Tak | _ *US003** | **1** |
| *(Puste)* | ***1** _ | _*_Tak: US002_*_ | Nr | US003 | 3 | Nr | _ *US002** | **1** |
| *(Puste)* | ***1** _ | _*_Tak: US002_*_ | Nr | US003 | 3 | Nr | _ *US002** | **1** |
| *(Puste)* | 1 | Nr | Tak: 2 | ***US003** _ | _*_3_*_ | Nr | _ *US003** | **3** |
| *(Puste)* | 1 | Nr | ***Tak: 2** _ | _*_US003_*_ | 3 | Tak | _ *US003** | **2** |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Umowy zakupu](../../procurement/purchase-agreements.md)
