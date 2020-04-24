---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu
description: Ten temat pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c39d383c15bcc838e09bc417f7e961c3647828da
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213292"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu

[!include [banner](../../includes/banner.md)]

Ten temat pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru. Zazwyczaj zadanie wykonuje projektant produktów.


## <a name="create-a-product-number-nomenclature"></a>Tworzenie konwencji nazewnictwa numerów produktu
1. Wybierz **Definicja modelu wariantu produktu**.
2. Wybierz **Nazewnictwo produktów**.
3. Wybierz pozycję **Nowy**.
4. W polu **Nazwa** wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład `ColorSize`.
5. W polu **Opis** wpisz wartość.
6. Wybierz opcję **Dodaj**.
7. Wybierz numer **produktu głównego**.
8. Wybierz opcję **Dodaj**.
9. Wybierz **Stała tekstowa**.
10. W polu **Tekst** wpisz wartość.
11. Wybierz opcję **Dodaj**.
12. Wybierz **Kolor**.
13. Wybierz opcję **Dodaj**.
14. Wybierz **Stała tekstowa**.
15. W polu **Tekst** wpisz wartość.
16. Wybierz opcję **Dodaj**.
17. Wybierz **Rozmiar**.
18. Zamknij stronę.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Przypisywanie konwencji nazewnictwa do produktu głównego
1. Wybierz **Grupy wymiarów produktu**.
2. Zaznacz grupę **wymiarów produktu SizeCol**.
3. Wybierz opcję **Edycja**.
4. W polu **Użyj nazewnictwa** zaznacz opcję **Tak**.
5. W polu **Nazewnictwo numerów wariantów produktu** wprowadź lub wybierz wartość.
6. Zamknij stronę.

