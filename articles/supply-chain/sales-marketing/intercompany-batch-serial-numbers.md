---
title: Międzyfirmowe numery partii i seryjne
description: W tym temacie wyjaśniono, co będzie się działo podczas rejestrowania numerów partii i numerów seryjnych dla zamówień międzyfirmowych
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548481"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Międzyfirmowe numery partii i seryjne

[!include [banner](../../includes/banner.md)]

Firmy, które używają numerów seryjnych lub numerów partii do śledzenia swoich towarów, muszą również śledzić numery seryjne i numery partii pobranych towarów. Funkcja międzyfirmowa automatyzuje nadawanie i pobieranie numerów seryjnych i numerów partii pomiędzy firmami. Po zarejestrowaniu numerów partii i numerów seryjnych towarów w międzyfirmowym zamówieniu sprzedaży można skonfigurować program tak, aby te numery były automatycznie przekazywane do międzyfirmowego zamówienia zakupu i oryginalnego zamówienia sprzedaży. Na stronie **Międzyfirmowe** dla zamówienia sprzedaży konfigurujesz odpowiednie parametry:

- Zaznaczenie pola **Numer partii** na stronie **Zasady zamówień sprzedaży** spowoduje zsynchronizowanie numeru partii z transakcjami magazynowymi w wierszach międzyfirmowego zamówienia zakupu podczas księgowania dokumentu dostawy międzyfirmowego zamówienia sprzedaży.
- Zaznaczenie pola **Numer seryjny** spowoduje zsynchronizowanie numeru seryjnego z transakcjami magazynowymi w wierszach międzyfirmowego zamówienia zakupu podczas księgowania dokumentu dostawy międzyfirmowego zamówienia sprzedaży.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
