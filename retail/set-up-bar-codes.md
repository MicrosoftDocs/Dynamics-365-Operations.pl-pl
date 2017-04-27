---
title: "Ustawianie kodów kreskowych"
description: "W tym artykule opisano, jak używać skanera kodów kreskowych w programie Microsoft Dynamics 365 for Operations — Handel detaliczny."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 7734a08756f5b737744f9c8ce1d358be020b859f
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-codes"></a>Ustawianie kodów kreskowych

[!include[banner](includes/banner.md)]


W tym artykule opisano, jak używać skanera kodów kreskowych w programie Microsoft Dynamics 365 for Operations — Handel detaliczny.

Kodów kreskowych można używać do kupowania i sprzedawania produktów, śledzenia wariantów produktów oraz konfigurowania odbiorców i pracowników. Umożliwiają także wydawanie i zatwierdzanie kuponów, kart upominkowych i not kredytowych. Towary detaliczne można skonfigurować przy użyciu standardowych lub niestandardowych, wewnętrznych kodów kreskowych. Produkt może mieć więcej niż jeden kod kreskowy. Na przykład produkt może mieć wiele kodów kreskowych, gdy pochodzi od różnych producentów lub ma warianty, które są oparte na rozmiarze, kolorze lub stylu. Kody kreskowe mogą uwzględniać wagę lub cenę produktu. Maski kodu kreskowego są szablonami do tworzenia kodów kreskowych. **Uwaga:** Po przypisaniu unikatowego kodu kreskowego do każdej kombinacji wariantów można zeskanować w kasie kod kreskowy towaru i pozwolić programowi określić wariant produktu, który jest sprzedawany. Można także gromadzić i wyświetlać statystyki sprzedaży według wariantu. Każdej grupie rozmiarów, kolorów i stylów można przypisać unikatowy numer, który identyfikuje ją w kodzie kreskowym. Program Dynamics 365 for Operations używa masek kodów kreskowych do automatycznego generowania kodów kreskowych dla poszczególnych kombinacji wariantów. Funkcja ta może być przydatna w przypadku istnienia wielu rozmiarów, kolorów i stylów, ponieważ liczba kombinacji szybko wzrasta wraz z dodawaniem kodów wariantów. W przypadku niekorzystania z tej funkcji kody kreskowe trzeba ręcznie przypisywać poszczególnym kombinacjom reprezentującym warianty produktu. Kody kreskowe można tworzyć ręcznie lub automatycznie. Aby utworzyć kody kreskowe, należy wykonać następujące zadania w kolejności, w jakiej są one przedstawione.

1.  [Konfigurowanie znaków maski kodu kreskowego](set-up-bar-code-masks.md).
2.  [Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md).
3.  Konfigurowanie ustawień kodów kreskowych.
4.  Tworzenie kodów kreskowych dla produktów.


<a name="see-also"></a>Informacje dodatkowe
--------

[Ustawianie masek kodów kreskowych](set-up-bar-code-masks.md)




