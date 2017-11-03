---
title: "Ustawianie kodów kreskowych"
description: "W tym artykule opisano, jak używać skanera kodów kreskowych w programie Microsoft Dynamics 365 for Retail."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fdc56bf468babd4b0b0652d9791114af676c8470
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-bar-codes"></a>Konfigurowanie kodów kreskowych

[!include[banner](includes/banner.md)]


W tym artykule opisano, jak używać skanera kodów kreskowych w programie Microsoft Dynamics 365 for Retail.

Kodów kreskowych można używać do kupowania i sprzedawania produktów, śledzenia wariantów produktów oraz konfigurowania odbiorców i pracowników. Umożliwiają także wydawanie i zatwierdzanie kuponów, kart upominkowych i not kredytowych. Towary detaliczne można skonfigurować przy użyciu standardowych lub niestandardowych, wewnętrznych kodów kreskowych. Produkt może mieć więcej niż jeden kod kreskowy. Na przykład produkt może mieć wiele kodów kreskowych, gdy pochodzi od różnych producentów lub ma warianty, które są oparte na rozmiarze, kolorze lub stylu. Kody kreskowe mogą uwzględniać wagę lub cenę produktu. Maski kodu kreskowego są szablonami do tworzenia kodów kreskowych. **Uwaga:** Po przypisaniu unikatowego kodu kreskowego do każdej kombinacji wariantów można zeskanować w kasie kod kreskowy towaru i pozwolić programowi określić wariant produktu, który jest sprzedawany. Można także gromadzić i wyświetlać statystyki sprzedaży według wariantu. Każdej grupie rozmiarów, kolorów i stylów można przypisać unikatowy numer, który identyfikuje ją w kodzie kreskowym. Program Dynamics 365 for Retail używa masek kodów kreskowych do automatycznego generowania kodów kreskowych dla poszczególnych kombinacji wariantów. Funkcja ta może być przydatna w przypadku istnienia wielu rozmiarów, kolorów i stylów, ponieważ liczba kombinacji szybko wzrasta wraz z dodawaniem kodów wariantów. W przypadku niekorzystania z tej funkcji kody kreskowe trzeba ręcznie przypisywać poszczególnym kombinacjom reprezentującym warianty produktu. Kody kreskowe można tworzyć ręcznie lub automatycznie. Aby utworzyć kody kreskowe, należy wykonać następujące zadania w kolejności, w jakiej są one przedstawione.

1.  [Konfigurowanie znaków maski kodu kreskowego](set-up-bar-code-masks.md).
2.  [Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md).
3.  Konfigurowanie ustawień kodów kreskowych.
4.  Tworzenie kodów kreskowych dla produktów.


<a name="see-also"></a>Informacje dodatkowe
--------

[Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md)




