---
title: Stany cyklu życia produktu i transakcje
description: W tym temacie wyjaśniono, w jaki sposób można kontrolować, które transakcje są dozwolone dla poszczególnych stanów cyklu życia w trakcie przechodzenia produktu inżynieryjnego przez cykl życia.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEcoResProductLifecycleStateChange
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 989cfd3846e4921d24f5dcf809f1735d2cf62dbb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005334"
---
# <a name="product-lifecycle-states-and-transactions"></a>Stany cyklu życia produktu i transakcje

[!include [banner](../includes/banner.md)]

Ponieważ produkt inżynieryjny przechodzi przez swój cykl życia, ważne jest, aby mieć możliwość kontrolowania, które transakcje są dozwolone w każdym stanie cyklu życia. Na przykład produkty, które nie są jeszcze w stanie dojrzałym, nie powinny być umieszczane w zamówieniu sprzedaży. Alternatywnie, jeśli produkt zbliża się do stanu końcowego, możesz chcieć kontrolować dopływ tego produktu.

W przypadku produktu inżynieryjnego zmiany stanu cyklu życia są powiązane z wersjami inżynieryjnymi produktu. Dlatego stan cyklu życia produktu można również powiązać z jego wersjami technicznymi. Gdy stan cyklu rozwojowego produktu jest połączony z wersją inżynierską, można użyć stanu cyklu rozwojowego, aby kontrolować, które transakcje są dozwolone dla wersji inżynierskiej.

## <a name="create-and-manage-product-lifecycle-states"></a>Twórz stany cyklu życia produktu i zarządzaj nimi

Praca ze stanami cyklu życia produktu, przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Stan cyklu życia produktu**. Następnie wykonaj jeden z następujących kroków.

- Aby utworzyć nowy stan cyklu życia, wybierz opcję **Nowa** w okienku akcji, a następnie określ te pola zgodnie z poniższymi podsekcjami.
- Aby edytować istniejący stan cyklu życia, wybierz ją w okienku listy, wybierz opcję **Edytuj** w okienku akcji, a następnie określ pola w sposób opisany w poniższych podsekcjach.
- Aby usunąć istniejący stan cyklu życia, zaznacz go w okienku listy, a następnie wybierz **Usuń** w okienku akcji.

> [!NOTE]
> Produkty inżynieryjne korzystają z tych samych stanów cyklu życia, co produkty standardowe (nieinżynieryjne). Możesz także otworzyć **Stan cyklu życia produktu** stronę opisaną w tym temacie, przechodząc do **Zarządzanie informacjami o produkcie \> Konfiguracja \> Stan cyklu życia produktu**. Aby uzyskać więcej informacji o stanach cyklu życia produktu, zarówno dla produktów inżynieryjnych, jak i standardowych, zapoznaj się z [Omówienie stanów cyklu życia produktu](../pim/product-lifecycle.md).

### <a name="header"></a>Nagłówek

Określ następujące pola w nagłówku stanu cyklu życia produktu.

| Pole | opis |
|---|---|
| Stanowy | Umożliwia wprowadzenie nazwy stanu cyklu życia produktu. |
| opis | Umożliwia wprowadzenie opisu stanu cyklu życia produktu. |

### <a name="general-fasttab"></a>Skrócona karta Ogólne

Skonfiguruj następujące pola na skróconej karcie **Ogólne**.

| Pole | opis |
|---|---|
| Domyślnie po zwolnieniu do firmy | W przypadku produktów standardowych ustawienie tej opcji na wartość *Tak* powoduje, że ten stan cyklu życia powinien być stosowany domyślnie do wszystkich produktów, gdy są one zwalniane po raz pierwszy. Ustaw na *Nie*, jeśli ten stan cyklu życia zostanie zastosowany ręcznie później.<p>To ustawienie nie dotyczy produktów inżynieryjnych. Stan cyklu życia w wersji produktu inżynierskiego po jej utworzeniu w firmie inżynierskiej jest określony w kategorii zmiany technologiczne. Gdy produkt jest zwalniany do firmy operacyjnej, kopiowany jest stan cyklu życia produktu. Innymi słowy, gdy produkt inżynieryjny jest zwalniany do firmy operacyjnej, ma taki sam stan cyklu życia, jak w firmie inżynierskiej. Stan cyklu życia można zastąpić w firmie operacyjnej.</p> |
| Jest aktywna dla planowania | Ustawienie tej opcji na wartość *Tak* powoduje uwzględnienie produktów, które są w tym stanie cyklu życia w obliczeniach na poziomach planowania głównego i BOM. Ustawienie wartości *Nie* powoduje wykluczania z obliczeń produktów, które są w tym stanie cyklu życia. |

### <a name="enabled-business-processes-fasttab"></a>Skrócona karta Włączanie procesów biznesowych

Za pomocą skróconej karty **Włączanie procesów biznesowych** można określić, które z dostępnych procesów biznesowych mogą być używane w przypadku produktów w bieżącym stanie cyklu życia. Procesy wymienione na tej skróconej karcie są automatycznie odnajdywane w następujący sposób:

- Po pierwszym zapisaniu nowego stanu cyklu życia strona ładuje obecnie dostępne procesy biznesowe.
- Jeśli dodasz nowe procesy biznesowe do swojego systemu, możesz zaktualizować listę na **Włączone procesy biznesowe** skróconą kartę dla istniejącego stanu cyklu życia, wybierając **Sprawdź dostępność aktualizacji** w okienku akcji.

Następujące pola są dostępne dla każdego procesu wymienionego na skróconej karcie **Włączanie procesów biznesowych**.

| Pole | opis |
|---|---|
| Przetwarzaj | To pole tylko do odczytu zawiera nazwę istniejącego procesu biznesowego. |
| Obszar procesu | To pole tylko do odczytu zawiera nazwę obszaru istniejącego procesu. |
| Zasady | Wybierz jedną z następujących wartości, aby określić, czy i w jaki sposób bieżący proces będzie dozwolony dla produktów znajdujących się w tym stanie cyklu życia:<ul><li>**Włączone** — proces biznesowy jest dozwolony.</li><li>**Zablokowano** — proces nie jest dozwolony. Jeśli użytkownik spróbuje użyć procesu na produkcie, który jest w tym stanie cyklu życia, system zablokuje próbę i zamiast tego wyświetli błąd. Na przykład można blokować produkty wycofane z eksploatacji od zakupu.</li><li>**Włączone z ostrzeżeniem** — proces jest dozwolony, ale zostanie wyświetlone ostrzeżenie. Na przykład możesz chcieć, aby prototypowy produkt został umieszczony w zleceniu produkcyjnym, które jest tworzone przez dział badań i rozwoju. Jednak inne działy powinny mieć świadomość, że nie powinni jeszcze generować produktu.</li></ul> |

Jeśli dodajesz więcej reguł stanu cyklu życia jako dostosowanie, możesz wyświetlić te reguły w interfejsie użytkownika (UI), wybierając **Odśwież procesy** w górnym panelu. Przycisk **Odśwież procesy** jest dostępny tylko dla administratorów.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]