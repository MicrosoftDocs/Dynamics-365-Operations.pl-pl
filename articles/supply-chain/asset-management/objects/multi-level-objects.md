---
title: Wielopoziomowe składniki majątku
description: W tym temacie wyjaśniono, jak tworzyć i usuwać wielopoziomowe składniki majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a69fd8b7d81700a62ae96d679372b1d6c8a70bbf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253213"
---
# <a name="multi-level-assets"></a>Wielopoziomowe składniki majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono, jak tworzyć i usuwać wielopoziomowe składniki majątku. Składniki majątku i powiązane z nimi składniki podrzędne można tworzyć w hierarchicznej strukturze drzewa. W ten sposób można wyświetlać relacje i zależności między zasobami. Zadania konserwacji mogą być powiązane ze wszystkimi poziomami struktury drzewa. Statystyki mogą być również tworzone dla indywidualnego poziomu lub jako suma wszystkich poziomów podrzędnych składników majątku.

Na stronie listy **Wszystkie składniki majątku** (**Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki**) kolumna **Składnik majątku** zawiera listę składników majątku w porządku hierarchicznym. Kolumna **Nadrzędny** pokazuje pokrewny składnik nadrzędny. Ponadto jeśli składnik majątku i składnik podrzędny zostały utworzone , sekcja **Drzewo składników majątku** w okienku **Powiązane informacje** pokazuje składniki majątku w strukturze drzewa.

Aby uzyskać więcej informacji o tworzeniu składnika majątku, zobacz temat [Tworzenie składnika majątku](../objects/create-an-object.md). Aby utworzyć podrzędny składnik majątku, wybierz nadrzędny składnik majątku w polu **Nadrzędny** na skróconej karcie **Ogólne.**

## <a name="copy-an-asset-or-asset-structure"></a>Kopiowanie składnika majątku lub struktury składników majątku

Jeśli firma ma kilka podobnych struktur składników majątku, można użyć funkcji Kopiuj w module Zarządzanie składnikami majątku, aby szybko je utworzyć.

1. Wybierz kolejno **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku**.
2. Na stronie listy **Wszystkie składniki majątku** wybierz składnik majątku do skopiowania. Jeśli na przykład chcesz skopiować całą strukturę składników majątku, w tym podrzędne składniki majątku, wybierz nadrzędny składnik majątku.
3. Wybierz **Kopiuj składnik majątku**. W sekcji **Kopiuj z** pole **Składnik majątku** jest ustawione na składnik majątku wybrany na stronie listy.
4. W sekcji **Kopiuj do** w polu **Składnik majątku** wprowadź nazwę nowego składnika majątku.
5. Jeśli składnik majątku, który tworzysz powinien być częścią istniejącej struktury składników majątku, w sekcji **Nadrzędny składnik majątku** w polu **Składnik majątku** wybierz identyfikator nadrzędny.
6. Kliknij przycisk **OK**. Nowa struktura składników majątku jest wyświetlana na stronie listy **Wszystkie składniki majątku**. Wszystkie atrybuty składników majątku, plany konserwacji i serie czynności konserwacyjnych związane ze skopiowanym składnikiem majątku są przenoszone do nowego składnika majątku lub nowej struktury składników majątku.

Podczas kopiowania struktury składników majątku, podrzędny składnik majątku w nowej strukturze ma taką samą nazwę jak podrzędny składnik majątku, który został skopiowane. Po zakończeniu procedury kopiowania można łatwo zmienić nazwę i inne ustawienia dla składnika majątku. Wybierz składnik majątku na stronie listy **Wszystkie składniki majątku**, a następnie wybierz przycisk **Edytuj.**

> [!NOTE]
> Podczas kopiowania składnika majątku lub struktury składników majątku stan cyklu życia nowych składników majątku jest resetowany do dowolnego stanu zdefiniowanego jako początkowy stan cyklu życia składnika majątku. Lokalizacja czynności konserwacyjnych jest resetowana do domyślnej lokalizacji czynności konserwacyjnych.

## <a name="delete-an-asset-or-asset-structure"></a>Usuwanie składnika majątku lub struktury składników majątku

Jeśli składnik majątku ma powiązane podrzędne składniki majątku, można go usunąć tylko wtedy, gdy żadne żądania konserwacji, zadania zlecenia pracy, rejestracje błędów ani oceny warunków nie są rejestrowane na żadnym ze składników majątku.

1. Na stronie listy **Wszystkie składniki majątku** wybierz składnik majątku do usunięcia.
2. Wybierz opcję **Usuń**.

> [!NOTE]
> Jeśli nie można usunąć składnika majątku przy użyciu tej procedury, innym sposobem obsługi usuwania jest Konfigurowanie stanu cyklu życia składnika majątku w tym celu. Na przykład można skonfigurować stan cyklu życia jako **Uznany za odpadki** lub **Usunięty** na stronie **Stany cyklu życia składników majątku**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]