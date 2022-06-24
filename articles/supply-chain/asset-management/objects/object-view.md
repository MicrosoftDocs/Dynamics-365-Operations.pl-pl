---
title: Widok składnika majątku
description: W tym artykule opisano widok składnika majątku w Zarządzaniu składniami majątku.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTree, EntAssetFunctionalLocationTree
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a416dbea0bab8f6a506ae5cfbfc4feeae8edfe29
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882729"
---
# <a name="asset-view"></a>Widok składnika majątku

[!include [banner](../../includes/banner.md)]

 

W tym artykule opisano widok składnika majątku w Zarządzaniu składniami majątku. Strona **Widok składnika majątku** zawiera aktywne składniki majątku i lokalizacje czynności konserwacyjnych w widoku drzewa. W związku z tym można łatwo uzyskać przegląd relacji składników majątku do lokalizacji czynności konserwacyjnych. Ponadto można wyświetlić szczegółowe informacje o lokalizacjach czynności konserwacyjnych, składnikach majątku i powiązanych listach składowych (BOM). Można również uzyskać szybki przegląd aktywnych żądań konserwacji i zleceń pracy, które są związane ze składnikiem majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Widok składników majątku**.
2. Aby zmienić widok wyświetlany na stronie, wybierz nową wartość w polu **Widok.**

    > [!NOTE]
    > Domyślny widok wyświetlany po otwarciu strony **Widoku składników majątku** zależy od wartości wybranej w polu **Widok** na karcie **Składniki majątku** strony **Parametry zarządzania składnikami majątku** (**Zarządzanie składnikami majątku** \> **Ustawienia** \> **Parametry zarządzania składnikami majątku**).

Na skróconej karcie po prawej stronie będą widoczne szczegóły wybranego widoku.

Szlak nawigacyjny widoczny powyżej widoku drzewa pokazuje aktualne zaznaczenie w widoku drzewa. Ten szlak nawigacyjny używa następującego formatu:

Identyfikator lokalizacji czynności konserwacyjnych / Identyfikator lokalizacji czynności konserwacyjnych (jeśli jest więcej niż jedna lokalizacja czynności konserwacyjnych) \> Identyfikator składnika majątku / Identyfikator składnika majątku (jeśli jest więcej niż jeden składnik majątku) — numer elementu.

Jeśli masz wybrany składnik majątku w widoku drzewa, możesz wybrać **Aktywne żądania** lub **Aktywne zlecenia pracy**, aby wyświetlić żądania konserwacji lub zlecenia pracy, które są związane ze składnikiem majątku. Można również wybrać opcję **Otwórz** \> **Lokalizacja czynności konserwacyjnych**, **Składnik majątku** lub **BOM składnika majątku**, aby otworzyć powiązany widok.

Opcja **Lokalizacje czynności konserwacyjnych składnika majątku**, którą można wybrać w polu **Widok** jest również dostępna w dowolnym wyszukiwaniu składników majątku, w którym można wybrać składnik majątku. Widok drzewa jest wyświetlany na karcie **Widok składników majątku** na przykład podczas tworzenia [składnika majątku](../objects/create-an-object.md), żądania konserwacji lub zlecenie pracy.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]