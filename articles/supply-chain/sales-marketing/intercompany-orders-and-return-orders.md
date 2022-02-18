---
title: Międzyfirmowe zamówienia i zamówienia zwrotu
description: W tym temacie wyjaśniono zamówienia międzyfirmowe i zamówienia zwrotu
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
ms.openlocfilehash: 103225595e82bdedec6d97e5ebe5b61498377065
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548478"
---
# <a name="intercompany-orders-and-return-orders"></a>Międzyfirmowe zamówienia i zamówienia zwrotu

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób tworzenia i aktualizowania międzyfirmowych zamówień zakupu, zamówień sprzedaży, zamówień zwrotu, umów zakupu i umów sprzedaży.

## <a name="about-intercompany-orders"></a>Zamówienia międzyfirmowe — informacje

Gdy użytkownik tworzy międzyfirmowe zamówienie sprzedaży, system Microsoft Dynamics 365 Supply Chain Management automatycznie tworzy odpowiednie zamówienie zakupu. Podobnie utworzenie międzyfirmowego zamówienia zakupu powoduje automatyczne utworzenie odpowiedniego międzyfirmowego zamówienia sprzedaży.

Dotyczy to zamówień dwuetapowych (transakcje między dwiema powiązanymi firmami) i większości firm trójetapowych (gdy transakcja międzyfirmowa jest inicjowana ze zleceniem sprzedaży dla klienta zewnętrznego).

## <a name="intercompany-order-example"></a>Przykład zamówienia międzyfirmowego

Istnieją dwie powiązane firmy. Firma A jest oddziałem odpowiedzialnym za sprzedaż, a Firma B to podmiot zajmujący się dystrybucją. Międzyfirmowe zamówienia sprzedaży i zamówienia zakupu są tworzone automatycznie w następujących scenariuszach:

- Gdy firma A tworzy zamówienie zakupu, a dostawcą jest firma B, międzyfirmowe zamówienie sprzedaży jest tworzone automatycznie w firmie B. Dwuetapowy łańcuch zamówień składa się z zamówienia zakupu w firmie A i międzyfirmowego zamówienia sprzedaży w firmie B.
- Gdy firma B tworzy zamówienie sprzedaży, a klientem jest firma A, międzyfirmowe zamówienie zakupu jest tworzone automatycznie w firmie A. Dwuetapowy łańcuch zamówień składa się z zamówienia sprzedaży w firmie B i międzyfirmowego zamówienia zakupu w firmie A.
- Gdy firma A po raz pierwszy tworzy zamówienie sprzedaży dla klienta zewnętrznego, zamówienie zakupu może zostać utworzone automatycznie w firmie A. To z kolei powoduje automatyczne utworzenie międzyfirmowego zamówienia sprzedaży w firmie B. Trzyetapowy łańcuch zamówień składa się z zamówienie sprzedaży i zamówienie zakupu w firmie A oraz międzyfirmowe zamówienie sprzedaży w firmie B.

## <a name="about-intercompany-return-orders"></a>Międzyfirmowe zamówienia zwrotu — informacje

Pozycje międzyfirmowe można zwracać podobnie jak zwykłe zwroty. Jednak w przypadku towarów międzyfirmowych zamówienie zwrotu od klienta zewnętrznego tworzy międzyfirmowe zamówienie zakupu. To z kolei prowadzi do automatycznego tworzenia międzyfirmowego zamówienia zwrotu sprzedaży. Możesz również zwrócić towar międzyfirmowy bez zamówienia zwrotu od klienta zewnętrznego.

Międzyfirmowe zamówienia zwrotu, podobnie jak zwykłe zamówienia zwrotu, są inicjowane na stronie **Utwórz zamówienie zwrotu**.

W Microsoft Dynamics 365 Supply Chain Management międzyfirmowe umowy sprzedaży i zakupu są automatycznie aktualizowane w celu odzwierciedlenia zwróconego towaru. Zobowiązanie umowy sprzedaży lub zakupu dla tego towaru jest automatycznie dostosowywane w celu odzwierciedlenia zmiany ilości lub kwoty po zwróceniu towaru.

## <a name="intercompany-return-order-example"></a>Przykład zamówienia zwrotu międzyfirmowego

Firma A tworzy zamówienie zakupu, które jest połączone z umową zakupu dla towaru międzyfirmowego. Międzyfirmowe zamówienie sprzedaży jest automatycznie tworzone w firmie B, które jest połączone z odpowiednią umową sprzedaży. Umowa kupna i umowa sprzedaży są powiązane jako umowy wewnątrzgrupowe.

Firma A zwraca towar międzyfirmowy do firmy B. Firma B tworzy zamówienie zwrotu towaru, a zamówienie zwrotu zakupu jest automatycznie tworzone w firmie A. Zobowiązania dotyczące zarówno umowy zakupu, jak i umowy sprzedaży, które są połączone z oryginalnymi zamówieniami są automatycznie dostosowywane w celu odzwierciedlenia zmiany ilości lub kwoty.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]