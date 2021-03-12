---
title: Konfigurowanie kodów kreskowych
description: W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 86a29935974fbe30947c089d161f024428230b51
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969783"
---
# <a name="set-up-bar-codes"></a>Konfigurowanie kodów kreskowych

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak używać skanera kodów kreskowych w programie Dynamics 365 Commerce.

Kodów kreskowych można używać do kupowania i sprzedawania produktów, śledzenia wariantów produktów oraz konfigurowania odbiorców i pracowników. Umożliwiają także wydawanie i zatwierdzanie kuponów, kart upominkowych i not kredytowych. Towary można skonfigurować przy użyciu standardowych lub niestandardowych, wewnętrznych kodów kreskowych. Produkt może mieć więcej niż jeden kod kreskowy. Na przykład produkt może mieć wiele kodów kreskowych, gdy pochodzi od różnych producentów lub ma warianty, które są oparte na rozmiarze, kolorze lub stylu. Kody kreskowe mogą uwzględniać wagę lub cenę produktu. Maski kodu kreskowego są szablonami do tworzenia kodów kreskowych.

> [!NOTE]
> Po przypisaniu unikatowego kodu kreskowego do każdej kombinacji wariantów można zeskanować w kasie kod kreskowy towaru i pozwolić programowi określić wariant produktu, który jest sprzedawany. Można także gromadzić i wyświetlać statystyki sprzedaży według wariantu. Każdej grupie rozmiarów, kolorów i stylów można przypisać unikatowy numer, który identyfikuje ją w kodzie kreskowym. Usługa Commerce używa masek kodów kreskowych do automatycznego generowania kodów kreskowych dla poszczególnych kombinacji wariantów. Funkcja ta może być przydatna w przypadku istnienia wielu rozmiarów, kolorów i stylów, ponieważ liczba kombinacji szybko wzrasta wraz z dodawaniem kodów wariantów. W przypadku niekorzystania z tej funkcji kody kreskowe trzeba ręcznie przypisywać poszczególnym kombinacjom reprezentującym warianty produktu.

Kody kreskowe można tworzyć ręcznie lub automatycznie. Aby utworzyć kody kreskowe, należy wykonać następujące zadania w kolejności, w jakiej są one przedstawione.

1. [Konfigurowanie znaków maski kodu kreskowego](set-up-bar-code-masks.md).
2. [Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md).
3. Konfigurowanie ustawień kodów kreskowych.
4. [Tworzenie kodów kreskowych dla produktów](../supply-chain/pim/tasks/create-bar-code-product.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie masek kodów kreskowych](set-up-bar-code-masks.md)
