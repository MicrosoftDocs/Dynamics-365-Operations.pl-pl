---
title: Aktualizowanie faktur w związku ze zwrotami
description: Ta funkcjonalność obsługuje również procesy biznesowe w organizacjach, które określą, że zamówienia zwrotu i zamówienia sprzedaży mają być fakturowane w tym samym czasie i przez tę samą osobę.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec803aaa2f750c43a1865c9536730b275e6ef1d4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202153"
---
# <a name="perform-invoice-updates-for-returns"></a>Aktualizowanie faktur w związku ze zwrotami 

[!include [banner](../includes/banner.md)]


Zamówienie zwrotu to rodzaj zamówienia sprzedaży, które jest oznaczone jako zwrot towaru. Z tego względu do generowania faktur dla zamówień zwrotu jest używana strona listy **Wszystkie zamówienia sprzedaży**, a nie formularz **Zamówienia zwrotu**. Ta funkcjonalność obsługuje również procesy biznesowe w organizacjach, które określą, że zamówienia zwrotu i zamówienia sprzedaży mają być fakturowane w tym samym czasie i przez tę samą osobę.

Ponieważ faktura dla zwróconego towaru jest na kwotę ujemną, jest nazywana fakturą korygującą.

W przypadku skonfigurowania wsadowego przetwarzania aktualizacji faktur zamówienie sprzedaży typu **Zwrot towaru** musi zawierać wiersz zwrotu o stanie **Otrzymano**, co oznacza, że dokument dostawy zamówienia został zaktualizowany.

## <a name="post-an-invoice-for-a-return-order"></a>Księgowanie faktury dla zamówienia zwrotu

1.  Kliknij kolejno opcje **Rozrachunki z odbiorcami** \> **Wspólne** \> **Zamówienia sprzedaży** \> **Wszystkie zamówienia sprzedaży**.

2.  Zaznacz zamówienie sprzedaży, dla którego w polu **Typ zamówienia** jest wyświetlana wartość **Zamówienie zwrotu**.

3.  W okienku akcji na karcie **Faktura** w grupie **Generuj** kliknij opcję **Faktura**.

4.  Na karcie **Parametry** zaznacz pole wyboru **Księgowanie**.

5.  Przejrzyj informacje w formularzu i wprowadź niezbędne zmiany.

6.  Kliknij przycisk **OK**. Faktura korygująca zostanie zaksięgowana.

## <a name="see-also"></a>Informacje dodatkowe

[Aktualizowanie dokumentów dostawy w związku ze zwrotami](packing-slip-updates-returns.md)

  


