---
title: Konfigurowanie parametrów księgowania zamówienia międzyfirmowego
description: W tym temacie wyjaśniono, jak skonfigurować parametry, aby opublikować zamówienie międzyfirmowe
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
ms.openlocfilehash: 24389d8ed3768089d59dc87e5948e9ea7fa1ecfc
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679255"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Konfigurowanie parametrów księgowania zamówienia międzyfirmowego

[!include [banner](../../includes/banner.md)]

Po zaksięgowaniu międzyfirmowej faktury dla odbiorcy można ją skonfigurować tak, aby automatycznie księgowała zarówno międzyfirmowe zamówienie zakupu, jak i oryginalną fakturę dla odbiorcy.

> [!NOTE]
> Przed wykonaniem tej procedury skonfiguruj zarządzanie drukowaniem w swojej organizacji tak, aby wskazywało właściwą drukarkę faktur. Spowoduje to wydrukowanie faktury dla oryginalnego zamówienia sprzedaży na właściwej drukarce.

Należy skonfigurować następujące parametry:

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**. Wybierz zamówienie sprzedaży, z którym chcesz pracować.
1. W zamówieniu sprzedaży w okienku akcji wybierz **widok nagłówka**, a następnie wybierz skróconą kartę Ustawienia **międzyfirmowe** i otwórz ją.
1. Następnie, w okienku akcji, na karcie **Zamówienia sprzedaży** wybierz **Edytuj**.
1. Wróć do skróconej karty **Ustawienia międzyfirmowe** i wybierz opcję **Dostawa bezpośrednia**, aby umożliwić dostawę bezpośrednią w całym łańcuchu międzyfirmowym (dla wszystkich zamówień).
1. Wybierz **przycisk Zapisz**, aby zapisać zamówienie sprzedaży z nowym ustawieniem. Następnie wybierz **przycisk Zamknij**, aby zamknąć zamówienie sprzedaży.
1. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**. Na **karcie Ogólne** wybierz pozycję **Międzyfirmowe**.
1. Na stronie listy **Międzyfirmowe** wybierz łącze **Zasady zamówień zakupu**. W grupie pól **Międzyfirmowe zamówienie zakupu (dostawa bezpośrednia)** wybierz opcję **Księguj fakturę automatycznie** i usuń znacznik wyboru w polu **Drukuj fakturę automatycznie**.
1. W grupie pól **Oryginalne zamówienie sprzedaży (dostawa bezpośrednia)** wybierz opcję **Księguj fakturę automatycznie** i pole **Drukuj fakturę automatycznie**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
