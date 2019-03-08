---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu
description: Ten przewodnik pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "364886"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ten przewodnik pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru. Zazwyczaj zadanie wykonuje projektant produktów.


## <a name="create-a-product-number-nomenclature"></a>Tworzenie konwencji nazewnictwa numerów produktu
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Nazewnictwo produktów.
3. Kliknij przycisk Nowy.
4. W polu Nazwa wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład KolorRozmiar.
5. Wypełnij pole Opis.
6. Kliknij przycisk Dodaj.
7. Kliknij opcję Numer produktu głównego.
8. Kliknij przycisk Dodaj.
9. Kliknij opcję Stała tekstowa.
10. W polu Tekst wpisz wartość.
11. Kliknij przycisk Dodaj.
12. Kliknij opcję Kolor.
13. Kliknij przycisk Dodaj.
14. Kliknij opcję Stała tekstowa.
15. W polu Tekst wpisz wartość.
16. Kliknij przycisk Dodaj.
17. Kliknij opcję Rozmiar.
18. Zamknij stronę.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Przypisywanie konwencji nazewnictwa do produktu głównego
1. Kliknij opcję Grupy wymiarów produktu.
2. Zaznacz grupę wymiarów produktu SizeCol.
3. Kliknij przycisk Edytuj.
4. W polu Użyj nazewnictwa zaznacz opcję Tak.
5. W polu Nazewnictwo numerów wariantów produktu wprowadź lub wybierz wartość.
6. Zamknij stronę.

