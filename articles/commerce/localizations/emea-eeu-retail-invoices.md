---
title: Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w krajach wschodnioeuropejskich
description: W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.
author: epopov
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: f79208b2508ed3879aa626389564b10a1d78c165
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798828"
---
# <a name="customer-invoices-and-return-sales-orders-in-eastern-european-countries"></a>Faktury dla odbiorcy i zwrotne zamówienia sprzedaży w krajach wschodnioeuropejskich


[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób konfigurowania informacji do faktur dla odbiorców i zwrotnych zamówień sprzedaży w krajów środkowoeuropejskich.

Można skonfigurować następujące informacje dla faktur dla odbiorcy i zwrotnych zamówień sprzedaży, które są generowane w aplikacji Retail Point of Sale (POS):

- Można użyć grup podatków do przetwarzania zwrotów za pomocą zwrotnych zamówień sprzedaży. Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**. Otwórz kartę **Księgowanie \> Faktura**, a następnie ustaw opcję **Użyj grupy podatków dla zwrotów** na **Tak**.

    * Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę, na stronie **Odbiorcy** na skróconej karcie **Commerce** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków. Podczas księgowania zwrotnego zamówienia sprzedaży dla wybranego odbiorcy wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono w formularzu **Odbiorcy**.
    * Aby określić grupę podatków dla zwrotów dokonywanych przez odbiorcę w aplikacji POS w punkcie sprzedaży, na stronie **Sklepy** na skróconej karcie **Ogólne** w polu **Grupa podatków dla zwrotów** wybierz grupę podatków. Podczas księgowania zwrotnego zamówienia sprzedaży dla odbiorcy ze sklepu wiersz zwrotnego zamówienia sprzedaży zostanie zaktualizowany przez grupę podatków dla zwrotów, którą określono na stronie **Sklepy**.

- Można użyć daty księgowania faktury dla odbiorcy sieci sprzedaży lub zwrotnego zamówienia sprzedaży jako daty faktury sprzedaży lub zwrotu, jeśli faktura lub zwrot nie ma domyślnej daty sprzedaży. Wybierz kolejno opcje **Commerce \> Ustawienia central \> Parametry \> Parametry Commerce**. Otwórz kartę **Księgowanie \> Faktura**, a następnie ustaw opcję **Użyj daty księgowania jako daty sprzedaży** na **Tak**.
- Można użyć zakresu numerów dostarczonego przez urzędy skarbowe w celu numerowania faktur dla odbiorcy z Łotwy i Litwy i zwrotnych zamówień sprzedaży.

    * Wybierz kolejno opcje **Administrowanie organizacją \> Sekwencje numerów \> Zarządzanie licznikami**. Powinien istnieć rekord, gdzie **Moduł** = **Sprzedaż**, a **Typ** = **Faktura**.
    * Wybierz kolejno opcje **Administrowanie organizacją \> Sekwencje numerów \> Konfiguracja numerowania faktur**. Zaznacz pole wyboru **Hande** dla wiersza numeracji używanego do numerowania faktur dla odbiorców.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]