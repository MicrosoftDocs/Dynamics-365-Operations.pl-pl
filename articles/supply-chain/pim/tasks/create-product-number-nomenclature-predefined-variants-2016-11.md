---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu
description: Ten artykuł pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e77c8eabe1657f7fbfef71747627207dccff3b60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887320"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Tworzenie konwencji nazewnictwa identyfikatorów produktów dla wstępnie zdefiniowanych wariantów produktu

[!include [banner](../../includes/banner.md)]

Ten artykuł pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla wstępnie zdefiniowanych wariantów produktu i jak ją przypisać do odpowiedniej grupy wymiarów produktu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Nowa konwencja nazewnictwa numerów produktu jest przypisana do grupy wymiarów koloru i rozmiaru. Zazwyczaj zadanie wykonuje projektant produktów.


## <a name="create-a-product-number-nomenclature"></a>Tworzenie konwencji nazewnictwa numerów produktu

1. Wybierz kolejno pozycje **Zarządzanie informacjami o produktach \> Ustawienia \> Nazewnictwo produktów**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa** wprowadź nazwę konwencji nazewnictwa, która pomoże w identyfikacji docelowej grupy wymiarów produktu, na przykład `ColorSize`.
1. W polu **Opis** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz numer **produktu głównego**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Kolor**.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Stała tekstowa**.
1. W polu **Tekst** wpisz wartość.
1. Wybierz opcję **Dodaj**.
1. Wybierz **Rozmiar**.
1. Zamknij stronę.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Przypisywanie konwencji nazewnictwa do produktu głównego

1. Wybierz **Grupy wymiarów produktu**.
2. Zaznacz grupę **wymiarów produktu SizeCol**.
3. Wybierz opcję **Edycja**.
4. W polu **Użyj nazewnictwa** zaznacz opcję **Tak**.
5. W polu **Nazewnictwo numerów wariantów produktu** wprowadź lub wybierz wartość.
6. Zamknij stronę.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]