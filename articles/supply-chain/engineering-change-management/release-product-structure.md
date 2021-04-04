---
title: Zwalnianie struktur produktu
description: W tym temacie oprócz zwalniania produktów razem z ich wersjami konstrukcyjnymi, wyjaśniono również, jak można zwolnić kompletne struktury produktu. W ten sposób można zagwarantować, że przydatne dane konstrukcyjne dotyczące produktów mogą być łatwo używane w różnych firmach.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductReleaseSiteBulkEdit, EngChgProductReleaseSendListPage, EngChgProductReleaseSendDetails,EngChgProductReleaseSelection,EngChgProductReleaseReceiveListPage, EngChgProductReleaseReceiveDetails, EngChgProductReleasePreviewPane, EngChgProductReleasePolicy, EngChgProductReleasePart, EngChgProductReleaseNote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: c1304d3277e12bc602fa5bc25a61e1f95edba59c
ms.sourcegitcommit: 4835acc3edacf8277937723d3f85a7875bd8de83
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/11/2021
ms.locfileid: "5580922"
---
# <a name="release-product-structures"></a>Zwalnianie struktur produktu

[!include [banner](../includes/banner.md)]

Aby zapewnić możliwość ponownego wykorzystania danych produktów istotnych z punktu widzenia inżynierii w różnych firmach, oprócz wydawania produktów wraz z ich wersjami technicznymi można zwolnić pełne struktury produktów. Można więc zwolnić wielopoziomowe struktury list składowych (BOM) razem z elementem nadrzędnym akcji w ramach jednego zwolnienia. W takim przypadku BOM i produkty niższego poziomu są również zwolnione.

Produkty inżynieryjne są tworzone i obsługiwane przez ich firmę inżynieryjną w taki sposób, aby spełniały wymagania jakościowe w momencie ich projektowania. Każda firma operacyjna produkująca produkt musi mieć ten sam produkt i podstawowy BOM. W zależności od zakładu produkcyjnego trasa może zostać utworzona lokalnie. W takim przypadku nie można zwolnić trasy razem z produktem. W przypadku firm, które będą sprzedawać produkty, ale nie będą ich produkować, BOM może nie być wymagany.

Aby ten proces był bardziej wydajny, wszystkie dane istotne z punktu widzenia inżynierii mogą być udostępniane w tym samym czasie innym firmom operacyjnym. Te dane obejmują strukturę produktu. Podczas procesu zwalniania można wybrać, która część danych produktu powinna zostać zwolniona.

Aby uzyskać więcej informacji na temat firm inżynieryjnych i firm operacyjnych, zapoznaj się z [firmami inżynierskimi i regułami własności danych](engineering-org-data-ownership-rules.md).

Należy zauważyć, że można wydać zarówno produkty standardowe, jak i produkty inżynieryjne wraz z wersją struktury produktu. W trakcie tego procesu cała struktura produktu zostanie zwolniona, nawet BOM i trasa z firmy, w której są one zwalniane.

Aby zapoznać się z przykładem zwolnienia produktu, przeczytaj temat [Zwalnianie produktu inżynieryjnego do firmy lokalnej](engineering-scenarios.md#release)

## <a name="released-data-for-a-product-when-the-release-product-structure-is-used"></a>Dane zwolnione dla produktu, gdy jest używana struktura zwalnianego produktu

Do zwalniania produktów inżynieryjnych dołączane są następujące dane:

- **Dane produktu** — tworzony jest nowy zwolniony produkt.
- **Dane w wersji inżynieryjnej** — wersja inżynieryjna i jej dane jest tworzona lub aktualizowana. Należy zauważyć, że po ponownym zwolnieniu tej samej wersji inżynieryjnej dla firmy operacyjnej dane techniczne zostaną zastąpione.
- **Atrybuty technologiczne** — tworzone lub aktualizowane są atrybuty technologiczne i ich wartości.
- **Inżynieryjna lista składowa (BOM)** — Inżynieryjny BOM i jego wiersze można tworzyć lub aktualizować. Aby uzyskać więcej informacji o własności danych, należy zapoznać się z [Właściciele produktów](product-owner.md).
- **Trasy inżynieryjne** — Trasy inżynieryjne i ich operacje można tworzyć lub aktualizować. Aby uzyskać więcej informacji o własności danych, należy zapoznać się z [Właściciele produktów](product-owner.md).
- **Dokumenty techniczne** — dokumenty technologiczne, które są połączone z wersją inżynieryjną, są tworzone lub aktualizowane.

Po włączeniu zarządzania zmianami inżynierskimi w systemie dostępna jest wersja produktu. Ponadto standardowe produkty będą zawierać BOM-y i trasy, gdy zostaną wydane.

## <a name="product-acceptance"></a>Akceptacja produktu

**Akceptacja produktu** jest kluczowym parametrem wpływającym na proces zwalniania. Ten parametr można określić dla każdej firmy, przechodząc do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Parametry zarządzania zmianami projektowymi**. Aby uzyskać więcej informacji, zobacz [Parametry zarządzania zmianami projektowymi](engineering-parameters.md).

### <a name="automatic-product-acceptance"></a>Automatyczna akceptacja produktu

Poszczególne wydania produktów inżynieryjnych są wydawane, gdy ktoś z firmy inżynierskiej wybierze produkt do zwolnienia. Jeśli parametr **Akceptacja produktu** jest ustawiany na *Automatyczne*, użytkownik w firmie inżynierskiej decyduje, które dane produktu powinny zostać automatycznie zwolnione do firm operacyjnych. Produkt zostanie automatycznie zwolniony do firm wybranych w kreatorze zwolnień.

### <a name="manual-product-acceptance"></a>Ręczna akceptacja produktu

Poszczególne wydania produktów inżynieryjnych są wydawane, gdy ktoś z firmy inżynierskiej wybierze produkt do zwolnienia. Jeśli parametr **Akceptacja produktu** jest ustawiany na *Ręcznie*, użytkownik w firmie inżynierskiej decyduje, które dane produktu powinny zostać zwolnione do firm operacyjnych. Następnie użytkownik z każdej firmy operacyjnej przegląda dane produktu i decyduje, czy zaakceptować zwolnienie. Podczas odbierania danych użytkownik w firmie operacyjnej może określić następujące opcje:

- Jeśli produkty (aktualizacje) nie są istotne dla firmy operacyjnej, użytkownik może zrezygnować z akceptacji tego wydania.
- Użytkownik może zmienić szablon pozycji dla nowych produktów.
- Użytkownik może wybrać, czy produkt powinien zostać zwolniony wraz z jego listami BOM i / lub trasami oraz czy mają być zwolnione jako zatwierdzone i aktywne.
- Użytkownik może zmienić daty wejścia w życie produktów.

Aby zapoznać się z przykładem sposobu zaakceptowania produktu, zapoznaj się z [Przejrzyj i zaakceptuj produkt przed wydaniem go w lokalnej firmie](engineering-scenarios.md#accept).

> [!NOTE]
> W przypadku produktów standardowych można zwolnić z dowolnej firmy do dowolnej innej firmy. W przypadku produktów inżynieryjnych jedyną firmą, z której można zwolnić, jest firma inżynieryjna.

## <a name="release-policies"></a>Zasady zwalniania

Nie wszystkie firmy operacyjne potrzebują tych samych danych produktu. Zwykle firmy operacyjne, które wytwarzają produkty inżynieryjne, wymagają BOM, natomiast firma operacyjna, która sprzedaje tylko produkty inżynieryjne, nie wymaga BOM. Zasady zwalniania umożliwiają ustanawianie parametrów używanych do zwalniania produktów.

Aby uzyskać więcej informacji na temat kategorii produktów inżynieryjnych, zapoznaj się z tematem [Wersje inżynieryjne i kategorie produktów inżynieryjnych](engineering-versions-product-category.md).

Podczas procesu zwalniania można mieć wpływ na ustawienia.

## <a name="create-and-manage-product-release-policies"></a>Tworzenie zasad zwalniania produktów i zarządzanie nimi

Aby pracować z zasadami wydania produktów, przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> zasady zwalniania produktów**. Następnie wykonaj jeden z następujących kroków.

- Aby utworzyć nową zasadę, wybierz opcję **Nowa** w okienku akcji, a następnie określ te pola zgodnie z poniższymi podsekcjami.
- Aby edytować istniejącą zasadę, wybierz ją w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie określ pola w sposób opisany w poniższych podsekcjach.
- Aby usunąć istniejącą zasadę, wybierz ją w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie na skróconej karcie **Ogólne** upewnij się, że opcja **Aktywne** jest ustawiona na wartość *Nie*. Następnie w okienku akcji wybierz opcję **Usuń**.

### <a name="header"></a>Nagłówek

Określ następujące pola w nagłówku zasady wydania produktu.

| Pole | opis |
|---|---|
| Imię i nazwisko | Wprowadź nazwę zasady. |
| opis | Wprowadź opis zasady. |

### <a name="general-fasttab"></a>Skrócona karta Ogólne

Określ następujące pola na karcie skróconej **Ogólne**, należącej do zasady wydania produktu.

| Pole | opis |
|---|---|
| Typ produktu | Umożliwia określenie, czy zasady dotyczą produktów typu *Towar* czy *Usługa*. Nie można zmienić tego ustawienia po zapisaniu rekordu. |
| Zastosuj szablony | Wybierz jedną z następujących opcji, aby określić, czy i w jaki sposób mają być stosowane szablony wersji produktu, gdy jest używana zasada:<ul><li>**Zawsze** — W przypadku wydań zawsze należy używać produktu wydanego według szablonu. W przypadku wybrania tej opcji należy użyć skróconej karty **Wszystkie produkty**, aby określić szablon używany dla każdej firmy, do której zostanie wydane zwolnienie. Jeśli szablon nie zostanie określony dla każdej firmy, która jest wymieniona na skróconej karcie **Wszystkie produkty**, podczas próby zapisania zasady pojawi się komunikat o błędzie.</li><li>**Opcjonalne** — Jeśli szablon zwolnionego produktu jest określony dla firmy wymienionej na skróconej karcie **Wszystkie produkty**, ten szablon będzie używany po zwolnieniu do tej firmy. W przeciwnym razie nie zostanie użyty żaden szablon. Po wybraniu tej opcji można zapisać zasadę bez przypisywania szablonów do wszystkich firm. (Żadne ostrzeżenie nie będzie wyświetlane.)</li><li>**Nigdy** — Żaden szablon zwolnionego produktu nie będzie używany dla żadnej firmy, do której będzie zwalniany towar, nawet jeśli szablon jest określony dla firm wymienionych na skróconej karcie **Wszystkie produkty**. Kolumny szablonów będą niedostępne.</li></ul> |
| Aktywni | Ta opcja służy do obsługi zasad zwolnienia. Ustaw tę opcję na wartość *Tak* dla wszystkich używanych zasad zwolnień. Jeśli zasada nie jest używana, należy wybrać opcję *Nie*, aby oznaczyć ją jako nie jako nieaktywną. Należy zauważyć, że nie można dezaktywować zasady zwalniania przypisanej do kategorii produktów inżynieryjnych i można usunąć tylko nieaktywne zasady zwalniania. |

### <a name="all-products-fasttab"></a>Skrócona karta Wszystkie produkty

Na skróconej karcie **Wszystkie produkty** należy dodać wiersz dla każdej firmy operacyjnej, która ma zostać użyta do zwolnienia tej zasady. Użyj przycisków na skróconej karcie **Wszystkie produkty**, aby dodać lub usunąć wiersze w razie konieczności. Dla każdego dodawanego wiersza należy określić następujące pola:

> [!NOTE]
> Ustawienia dotyczące skróconej karty **Wszystkie produkty** dotyczą zarówno produktów inżynieryjnych, jak i produktów standardowych.

| Pole | opis |
|---|---|
| Identyfikator kont firmy | Umożliwia wybranie firmy, której dotyczy dany wiersz. Parametry wiersza będą stosowane w przypadku, gdy produkty zostaną zwolnione do tej firmy. |
| Zwolniony produkt szablonowy | Dodaj szablon dla produktu. |
| Kopiuj zatwierdzenie BOM | To pole wyboru należy zaznaczyć, aby skopiować stan zatwierdzenia BOM do firmy odbierającej. |
| Kopiuj aktywację BOM | To pole wyboru należy zaznaczyć, aby skopiować stan aktywacji BOM do firmy odbierającej. |
| Kopiuj zatwierdzenie marszruty | To pole wyboru należy zaznaczyć, aby skopiować stan zatwierdzenia marszruty do firmy odbierającej.|
| Kopiuj aktywację marszruty | To pole wyboru należy zaznaczyć, aby skopiować stan aktywacji marszruty do firmy odbierającej. |

### <a name="option-parameters-for-engineering-products-fasttab"></a>Skrócona karta Parametry opcji dla produktów inżynieryjnych

Za każdym razem, gdy dodawany jest wiersz do skróconej karty **Wszystkie produkty**, tworzony jest również wiersz z odpowiadającą wartością **Identyfikator firmy** na skróconej karcie **Parametry opcji dla produktów inżynieryjnych**. Po usunięciu wiersza ze skróconej karty **Wszystkie produkty**, usuwany jest również wiersz z odpowiadającą wartością **Identyfikator firmy** na skróconej karcie **Parametry opcji dla produktów inżynieryjnych**.

Dla każdego wiersza wyświetlanego na skróconej karcie **Parametry opcji dla produktów inżynieryjnych** należy określić następujące pola:

> [!NOTE]
> Ustawienia skróconej karty **Parametry opcji dla produktów inżynieryjnych** dotyczą tylko produktów inżynieryjnych.

| Pole | opis |
|---|---|
| Szablon BOM | Po zwolnieniu produktu, który ma BOM, zostaną dodane wiersze określonego szablonu BOM. To pole jest przydatne przy dodawaniu składników lokalnych, takich jak pakowanie lub instrukcje w języku lokalnym. |
| Marszruta szablonu | Po zwolnieniu produktu, który ma marszrutę, zostaną dodane wiersze określonego szablonu. |
| Kopiuj obowiązywanie | Umożliwia określenie, czy daty obowiązywania powinny być kopiowane z firmy inżynierskiej do firmy operacyjnej podczas zwalniania produktów. |
| Automatycznie dodawaj do propozycji zwolnienia | To pole wyboru należy zaznaczyć dla produktów, które powinny być automatycznie zwalniane w ramach zlecenia zmiany inżynieryjnej. W ten sposób produkty należące do kategorii produktów inżynieryjnych korzystających z tej zasady wydania mogą być automatycznie zwalniane do firm operacyjnych, w których ta opcja jest skonfigurowana. (Aby uzyskać więcej informacji, zobacz [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).)

### <a name="review-each-product-when-you-release-it"></a>Przejrzyj każdy produkt po jego zwolnieniu

Podczas zwalniania produktów inżynieryjnych z BOM lub marszrutami parametry zostaną ustawione na wartości domyślne, zgodnie z zasadami zwalniania. Użytkownik może mieć wpływ na to zachowanie po stronie zwalniania podczas korzystania z struktury produktów zwolnienia.

Aby zwolnić produkty inżynieryjne, na stronie **Zwolnione produkty** wybierz produkty do zwolnienia, a następnie wybierz pozycję **Zwolnij strukturę produktu**, aby otworzyć Kreatora zwalniania. Na stronie **Wybierz produkty inżynieryjne do zwolnienia** są wyświetlane produkty. Wybierz jeden produkt, a następnie wybierz opcję **Szczegóły zwolnienia**, aby przejrzeć szczegóły dotyczące zwolnienia produktu.

Na stronie **Szczegóły zwolnienia** można zmienić wartość w polach **Przyjęcie BOM**, **Kopiuj zatwierdzenie BOM**, **Kopiuj aktywację BOM**, **Pobierz BOM**, **Kopiuj zatwierdzenie marszuty** i **Kopiuj aktywację marszruty**. W scenariuszu push-pull można zmienić wartość tych samych pól po stronie odbiorcy, pod warunkiem, że BOM i marszruta są zwolnione.

## <a name="product-owners-and-product-releases"></a>Właściciele produktów i zwolnienia produktów

Ponieważ właściciele produktów wiedzą, które podmioty prawne potrzebują ich produktów, produkt może zostać wydany tylko przez członków grupy właścicieli produktu. Inni użytkownicy nie mogą zwalniać produktów, jeśli nie są ich właścicielami.

To działanie ma zastosowanie tylko wtedy, gdy produkt jest bezpośrednio wybrany do zwolnienia. Produkty, które są częścią struktury innego produktu za pośrednictwem BOM, *mogą* być zwolnione przez użytkowników niebędących właścicielami po wydaniu produktu nadrzędnego, pod warunkiem, że są właścicielami produktu nadrzędnego.

Na przykład produkt X jest przypisany do grupy właścicieli *Szafy projektowe*. Produkt X jest również częścią BOM produktu Y, który jest przypisany do grupy właścicieli produktów *Głośniki projektowe*. Jeśli użytkownik z grupy właścicieli produktu *Głośniki projektowe* wyda produkt Y i jego BOM, produkt X zostanie zwolniony razem z produktem Y.

- Aby uzyskać więcej informacji, zobacz temat [Właściciele produktów](product-owner.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
