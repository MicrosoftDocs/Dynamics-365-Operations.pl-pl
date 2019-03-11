---
title: Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w aplikacji Retail w krajach środkowoeuropejskich
description: W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.
author: epopov
manager: annbe
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Retail, Operations
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 20ae19fb03acb075b6553b95808779c905bcd31b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371467"
---
# <a name="retail-customer-invoices-and-return-sales-orders-in-eastern-european-countries"></a>Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w aplikacji Retail w krajach środkowoeuropejskich


[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.

Można skonfigurować następujące informacje dla faktur dla odbiorcy i zwrotnych zamówień sprzedaży, które są generowane w aplikacji Retail Point of Sale (POS):

- Można użyć grup podatków do przetwarzania zwrotów za pomocą zwrotnych zamówień sprzedaży. Kliknij kolejno opcje **Handel detaliczny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży**. Otwórz kartę **Księgowanie > Faktura**, a następnie ustaw opcję **Użyj grupy podatków dla zwrotów** na **Tak**. 

  * Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę, na stronie **Odbiorcy** na skróconej karcie **Handel detaliczny** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków. Podczas księgowania zwrotnego zamówienia sprzedaży dla wybranego odbiorcy wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono w formularzu **Odbiorcy**.
  
  * Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę w aplikacji POS w punkcie sprzedaży, na stronie **Sklepy** na skróconej karcie **Ogólne** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków. Podczas księgowania zwrotnego zamówienia sprzedaży dla odbiorcy ze sklepu sieci sprzedaży wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono na stronie **Sklepy**.

- Można użyć daty księgowania faktury dla odbiorcy sieci sprzedaży lub zwrotnego zamówienia sprzedaży jako daty faktury sprzedaży lub zwrotu, jeśli faktura lub zwrot nie ma domyślnej daty sprzedaży. Kliknij kolejno opcje **Handel detaliczny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży**. Otwórz kartę **Księgowanie > Faktura**, a następnie ustaw opcję **Użyj daty księgowania jako daty sprzedaży** na **Tak**.

- Można użyć zakresu numerów dostarczonego przez urzędy skarbowe w celu numerowania faktur dla odbiorcy z Łotwy i Litwy i zwrotnych zamówień sprzedaży. 

  * Wybierz kolejno opcje **Administrowanie organizacją > Sekwencje numerów > Zarządzanie licznikami**. Powinien istnieć rekord, gdzie **Moduł** = **Sprzedaż**, a **Typ** = **Faktura**.

  * Wybierz kolejno opcje **Administrowanie organizacją > Sekwencje numerów > Konfiguracja numerowania faktur**. Zaznacz pole wyboru **Handel detaliczny** dla wiersza numeracji używanego do numerowania faktur dla odbiorców.
