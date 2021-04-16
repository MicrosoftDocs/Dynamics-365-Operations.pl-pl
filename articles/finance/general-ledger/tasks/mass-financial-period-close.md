---
title: Zbiorowe zamykanie okresów obrachunkowych
description: W tym temacie pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz.
author: aprilolson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54a5b16f731e850b468ea2e05e47b47774e45838
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826505"
---
# <a name="mass-financial-period-close"></a>Zbiorowe zamykanie okresów obrachunkowych

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz. Ponadto w zadaniu zostanie pokazane, jak ograniczyć księgowanie przez grupę użytkowników do określonych modułów.

1. W okienku nawigacji przejdź do **Moduły > Księga główna > Zamykanie okresu > Kalendarze księgi**. Należy zauważyć, że wyświetlana lista firm zależy od kalendarza obrachunkowego wybranego na stronie. Zostaną wyświetlone tylko firmy używające wybranego kalendarza obrachunkowego.
2. Wybierz opcję **Edycja**.
3. Wybierz okres, dla którego chcesz zmodyfikować stan.
4. Wybierz firmy, dla których chcesz zaktualizować stan. Możesz szybko wybrać wszystkie firmy zaznaczając znacznik wyboru w lewej górnej części siatki.  
5. Wybierz opcję **Aktualizuj dostęp do modułu**, aby zdefiniować uprawnienia księgowania do wybranego modułu. Stan modułu może być również aktualizowany jednostkowo poprzez edycję rekordów w siatce. Przycisk jest przydatny, gdy chcesz szybko aktualizować wiele rekordów firm.  
6. W module **Aplikacja** zaznacz moduł, któremu chcesz zaktualizować stan. Kliknij opcję **Wybierz**.
7. W polu poziom **Dostępu** zaznacz wartość **Wszystko**, **Brak** lub konkretną grupę użytkowników. Kliknij opcję **Wybierz**. Opcja Wszystko wskazuje, że wszyscy użytkownicy z prawem edycji modułu mogą księgować, jeśli okres jest otwarty. Opcja Brak wskazuje, że użytkownicy nie mogą księgować w module, jeśli okres jest otwarty. Zaznaczenie określonej grupy użytkowników oznacza, że tylko użytkownicy należący do grupy mogą księgować w module, jeśli okres jest otwarty.  
8. Wybierz **Aktualizuj**.
9. Wybierz inny okres, aby zaktualizować stan.
10. Wybierz firmy, dla których chcesz zaktualizować stan okresu.
11. Wybierz opcję **Aktualizuj stan okresu** i ustaw stan **Wstrzymane**, **Otwarte** lub **Trwale zamknięty**. **Otwarte** wskazuje, że można księgować w okresie, pod warunkiem, że użytkownik ma dostęp. Wartość **Wstrzymane** oznacza, że nie może księgować w okresie, ale okres można otworzyć ponownie. Wartość **Trwale zamknięty** oznacza, że okres jest zamknięty i już nigdy nie można go otworzyć. Nie można księgować korekt. Nie zaleca się ustawiania okresu na **Trwale zamknięty** do czasu zakończenia wszystkich korekt i inspekcji.  
12. Wybierz **Aktualizuj**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]