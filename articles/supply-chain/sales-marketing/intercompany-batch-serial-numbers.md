---
title: Międzyfirmowe numery partii i seryjne
description: W tym artykule wyjaśniono, co będzie się działo podczas rejestrowania numerów partii i numerów seryjnych dla zamówień międzyfirmowych
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5c743c8eee8d27a2c2357523a11236eb247ec5be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851515"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Międzyfirmowe numery partii i seryjne

[!include [banner](../../includes/banner.md)]

Firmy, które używają numerów seryjnych lub numerów partii do śledzenia swoich towarów, muszą również śledzić numery seryjne i numery partii pobranych towarów. Funkcja międzyfirmowa automatyzuje nadawanie i pobieranie numerów seryjnych i numerów partii pomiędzy firmami. Po zarejestrowaniu numerów partii i numerów seryjnych towarów w międzyfirmowym zamówieniu sprzedaży można skonfigurować program tak, aby te numery były automatycznie przekazywane do międzyfirmowego zamówienia zakupu i oryginalnego zamówienia sprzedaży. Na stronie **Międzyfirmowe** dla zamówienia sprzedaży konfigurujesz odpowiednie parametry:

- Zaznaczenie pola **Numer partii** na stronie **Zasady zamówień sprzedaży** spowoduje zsynchronizowanie numeru partii z transakcjami magazynowymi w wierszach międzyfirmowego zamówienia zakupu podczas księgowania dokumentu dostawy międzyfirmowego zamówienia sprzedaży.
- Zaznaczenie pola **Numer seryjny** spowoduje zsynchronizowanie numeru seryjnego z transakcjami magazynowymi w wierszach międzyfirmowego zamówienia zakupu podczas księgowania dokumentu dostawy międzyfirmowego zamówienia sprzedaży.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
