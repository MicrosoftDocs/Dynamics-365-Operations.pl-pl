---
title: Ustawianie opłat w międzyfirmowych zamówieniach
description: W tym temacie wyjaśniono, jak skonfigurować opłaty dla zamówień międzyfirmowych
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 27633e09bfcf41fbbe5449b0d3b5f283eaf7ee13
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673670"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Ustawianie opłat w międzyfirmowych zamówieniach

[!include [banner](../../includes/banner.md)]

Możesz skonfigurować opłaty, które mają być dodawane do zamówień międzyfirmowych. Po dodaniu opłaty do międzyfirmowego zamówienia sprzedaży jest ona automatycznie synchronizowana z międzyfirmowym zamówieniem zakupu. Działa to w obie strony — od międzyfirmowego zamówienia sprzedaży do zamówienia zakupu i na odwrót.

Możesz również użyć opłat, aby dodać zysk do międzyfirmowego zamówienia sprzedaży, definiując opłatę jako międzyfirmową wartość procentową.

Podczas konfigurowania opłat, które mają być stosowane do zamówień międzyfirmowych, włączasz obliczanie zysku wewnętrznego dla międzyfirmowego zamówienia sprzedaży na podstawie kwoty netto oryginalnego zamówienia sprzedaży. Możesz to zrobić, jeśli Twój dostawca międzyfirmowy sprzedaje Ci po kosztach własnych. Poniższa procedura opisuje, jak to zrobić dla klientów międzyfirmowych. Tę samą procedurę można zastosować dla dostawców.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia \> Opłaty \> Grupy opłat klienta**.
1. Utwórz grupę opłat.
1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**. Wybierz link do konta klienta. W okienku akcji wybierz kartę **Klient**, a następnie wybierz **Zamówienie sprzedaży** FastTab.
1. Wybierz **Edytuj** w okienku akcji, aby włączyć edycję pola. W polu **Grupa opłat** wybierz grupę opłat międzyfirmowych skonfigurowaną w kroku 2.
1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia \> Opłaty \> Opłaty automatyczne**.
1. Ustaw opłaty, wypełniając odpowiednie pola.
1. W polu **Relacje z klientem** wybierz grupę opłat międzyfirmowych skonfigurowaną w kroku 2.
1. Na skróconej karcie **Wiersze** w polu **Kategoria** wybierz opcję **Procent międzyfirmowy**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
