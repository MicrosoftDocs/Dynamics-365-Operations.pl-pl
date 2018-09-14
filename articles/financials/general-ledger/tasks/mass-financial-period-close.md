--- 
title: "Masowe zamykanie okresów obrachunkowych"
description: "W tej procedurze pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8d7151cbcd02f9312ca6b0de5e27231a0b0dc9d6
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="mass-financial-period-close"></a>Masowe zamykanie okresów obrachunkowych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób zawieszania okresu lub trwałego zamykania okresu albo więcej niż jednej firmy na raz. Ponadto w zadaniu zostanie pokazane, jak ograniczyć księgowanie przez grupę użytkowników do określonych modułów.

1. Wybierz kolejno opcje Księga główna > Zamykanie okresu > Kalendarze księgi.
    * Należy zauważyć, że wyświetlana lista firm zależy od kalendarza obrachunkowego wybranego na stronie. Zostaną wyświetlone tylko firmy używające wybranego kalendarza obrachunkowego.  
2. Kliknij przycisk Edytuj.
3. Wybierz okres, dla którego chcesz zmodyfikować stan.
4. Wybierz firmy, dla których chcesz zaktualizować stan.
    * Możesz szybko wybrać wszystkie firmy, zaznaczając znacznik wyboru w lewej górnej części siatki.  
5. Wybierz opcję Aktualizuj dostęp do modułu, aby zdefiniować uprawnienia księgowania do wybranego modułu.
    * Stan modułu może być również aktualizowany jednostkowo poprzez edycję rekordów w siatce. Przycisk jest przydatny, gdy chcesz szybko aktualizować wiele rekordów firm.  
6. W polu Moduł aplikacji zaznacz moduł, któremu chcesz zaktualizować stan. Kliknij opcję Wybierz.
7. W polu Poziom dostępu zaznacz wartość Wszystko, Brak lub konkretną grupę użytkowników. Kliknij opcję Wybierz.
    * Opcja Wszystko wskazuje, że wszyscy użytkownicy z prawem edycji modułu mogą księgować, jeśli okres jest otwarty. Opcja Brak wskazuje, że użytkownicy nie mogą księgować w module, jeśli okres jest otwarty. Zaznaczenie określonej grupy użytkowników oznacza, że tylko użytkownicy należący do grupy mogą księgować w module, jeśli okres jest otwarty.  
8. Kliknij przycisk Aktualizuj.
9. Wybierz inny okres, aby zaktualizować stan.
10. Wybierz firmy, dla których chcesz zaktualizować stan okresu.
11. Wybierz opcję Aktualizuj stan okresu i ustaw stan Wstrzymane, Otwarte lub Trwale zamknięty.
    * Opcja Otwarta wskazuje, że można księgować w okresie, pod warunkiem, że użytkownik ma dostęp. Wartość Wstrzymane oznacza, że nie może księgować w okresie, ale okres można otworzyć ponownie. Wartość Trwale zamknięty oznacza, że okres jest zamknięty i już nigdy nie można go otworzyć. Nie można księgować korekt. Nie zaleca się ustawiania okresu na Trwale zamknięty do czasu zakończenia wszystkich korekt i inspekcji.  
12. Kliknij przycisk Aktualizuj.


