---
title: Automatyczna rejestracja płatności za międzyfirmowe faktury dla odbiorcy
description: W tym temacie wyjaśniono, jak automatycznie rejestrować płatności dla faktur klientów międzyfirmowych
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
ms.openlocfilehash: ffc5c7bf44989fbcc18e940b5a7c9df81260d770
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548476"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Automatyczna rejestracja płatności za międzyfirmowe faktury dla odbiorcy

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management tworzy transakcję odbiorcy po zaksięgowaniu faktury międzyfirmowego klienta. Ta transakcja klienta pozostaje otwarta do czasu jej rozliczenia, co oznacza, że została zapłacona. Gdy odpowiednie międzyfirmowe zamówienie zakupu jest aktualizowane za pomocą faktury, tworzona jest transakcja dostawcy pasująca do transakcji odbiorcy. Ta transakcja dostawcy również pozostaje otwarta do czasu jej rozliczenia. Aby zredukować ryzyko niezgodności, istnieje możliwość automatycznego utworzenia i zaksięgowania arkusza płatności rozrachunków z odbiorcami po zaksięgowaniu arkusza płatności rozrachunków z dostawcami.

1. Przejdź do pozycji **Sprzedaż i marketing \> Odbiorcy \> Wszyscy odbiorcy**.
1. W okienku akcji na karcie **Ogólne** wybierz opcję **Międzyfirmowe**.
1. Aby skonfigurować międzyfirmowe płatności rozrachunków z odbiorcami na stronie **Międzyfirmowe** dla zamówień sprzedaży, wybierz **łącze Zasady zamówień sprzedaży**.
1. W polu **Arkusz płatności** wybierz arkusz płatności rozrachunków z odbiorcami, w którym chcesz zarejestrować międzyfirmowe płatności dostawców. Umożliwia wybór zespołu na stronie **Parametry modułu rozrachunków z odbiorcami**.
1. Aby księgować w tym arkuszu automatycznie, zaznacz pole **wyboru Księguj arkusz automatycznie**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
