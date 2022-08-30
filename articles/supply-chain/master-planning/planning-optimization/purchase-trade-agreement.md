---
title: Planowanie główne za pomocą umów handlowych zakupu
description: W tym artykule opisano sposób, w jaki Optymalizacja planowania może znaleźć dostawcę i/lub czas realizacji zamówienia planowanego na podstawie najlepszej ceny lub czasu realizacji, który znajduje się w umowach handlowych zakupu.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3797ee584cdb059a97670d532cf7e1a1163cc7ff
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335234"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Planowanie główne za pomocą umów handlowych zakupu

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób, w jaki Optymalizacja planowania może znaleźć dostawcę i/lub czas realizacji zamówienia planowanego na podstawie najlepszej ceny lub czasu realizacji, który znajduje się we wszystkich umowach handlowych zakupu, które zostały określone dla danego produktu.

## <a name="turn-the-purchase-trade-agreements-for-planning-optimization-feature-on-or-off"></a>Włącz lub wyłącz funkcję Umów handlowych zakupu na potrzeby Optymalizacji planowania

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.29, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Umowy handlowe dotyczące zakupu na potrzeby optymalizacji planowania* w obszarze roboczym [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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
> Optymalizacja planowania obsługuje wielowalutowe umowy handlowe. Podczas wyszukiwania umowy handlowej przy użyciu opcji **Najniższa cena jednostkowa** system uwzględni wiersze umowy handlowej zakupu z różnymi walutami, pod warunkiem że między walutą wiersza umowy handlowej a walutą rozliczeniową firmy został zdefiniowany kurs wymiany. W przeciwnym razie wiersz umowy handlowej będzie ignorowany i podczas planowania głównego będzie wyświetlany błąd. Dlatego planowanie główne będzie zawierać informacje ze wszystkich odpowiednich wierszy umowy handlowej zakupu, w których ceny mogą być konwertowane na walutę rozliczeniową. Należy pamiętać, że podczas konwersji cen wiersza umowy handlowej nie będą brane pod uwagę reguły zaokrąglania.

## <a name="examples-of-how-planning-optimization-finds-vendor-and-lead-times"></a>Przykłady zastosowania Optymalizacji planowania w odnalezieniu dostawcy i czasu realizacji

Poniższa tabela zawiera przykłady, które pokazują, jak różne ustawienia wydanego produktu i skojarzone z nim umowy handlowe zakupu wpływają na wartości znalezione dla wynikowego planowanego zamówienia zakupu. **Pogrubione** wartości w dwóch skrajnych kolumnach po prawej stronie to wartości wybrane przez Optymalizację planowania. Wartości **_pogrubione i zapisane kursywą_** w innych kolumnach to ustawienia, które wywołały wartości dla każdego wiersza.

| Zwolniony produkt: Dostawca | Domyślne ustawienia zamówień: Czas realizacji | Zapotrzebowanie na towar: Zastąp dostawcę | Zapotrzebowanie na towar: Zastąp czas realizacji | Umowa handlowa: Dostawca | Umowa handlowa: Czas realizacji | Umowa handlowa: Ignoruj czas realizacji | Wynikowy dostawca | Wynikowy czas realizacji |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001** _ | _*_1_*_ | Nie | Nie | US003 | 3 | Nie | _ *US001** | **1** |
| US001 | 1 | ***Tak: US002** _ | _*_Tak: 2_*_ | US003 | 3 | Nie | _ *US002** | **2** |
| *(Puste)* | 1 | Nie | Nie | ***US003** _ | _*_3_*_ | Nie | _ *US003** | **3** |
| *(Puste)* | ***1** _ | Nie | Nie | _*_US003_*_ | 3 | Tak | _ *US003** | **1** |
| *(Puste)* | ***1** _ | _*_Tak: US002_*_ | Nie | US003 | 3 | Nie | _ *US002** | **1** |
| *(Puste)* | ***1** _ | _*_Tak: US002_*_ | Nie | US003 | 3 | Nie | _ *US002** | **1** |
| *(Puste)* | 1 | Nie | Tak: 2 | ***US003** _ | _*_3_*_ | Nie | _ *US003** | **3** |
| *(Puste)* | 1 | Nie | ***Tak: 2** _ | _*_US003_*_ | 3 | Tak | _ *US003** | **2** |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Umowy zakupu](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
