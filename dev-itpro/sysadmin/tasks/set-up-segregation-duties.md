--- 
title: "Konfigurowanie podziału obowiązków"
description: "Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników."
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 2ab30f4326b627406f9a39d6c3203b181b67d68f
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-segregation-of-duties"></a>Konfigurowanie podziału obowiązków

[!include[task guide banner](../../includes/task-guide-banner.md)]

Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników. Ta koncepcja jest nazywana podziałem obowiązków. Na przykład można nie chcieć, aby ta sama osoba potwierdzała przyjęcie towarów i przetwarzała płatność dla dostawcy. Podział obowiązków pomaga zmniejszyć ryzyko oszustwa, a także wykrywać błędy lub nieprawidłowości. Podział obowiązków może także służyć do wymuszania zasad kontroli wewnętrznej. Aby utworzyć regułę, wykonaj procedurę opisaną poniżej. W celu wykonania procedury musisz być administratorem systemu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DAT. 

1. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Reguły podziału obowiązków.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
    * Nadaj nazwę regule.  
4. W polu Pierwszy obowiązek kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz pierwszy obowiązek, który będzie kontrolowany przez regułę.  
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Drugi obowiązek kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz drugi obowiązek, który będzie kontrolowany przez regułę.  
9. Na liście kliknij łącze w wybranym wierszu.
10. W polu Ważność wybierz opcję.
    * Wybierz priorytet ryzyka występującego wtedy, gdy ten sam użytkownik lub posiadacz roli wykonuje oba obowiązki.  
11. W polu Ryzyko związane z zabezpieczeniami wpisz wartość.
    * Wprowadź opis ryzyka związanego z zabezpieczeniami.  
12. W polu Ograniczenie zabezpieczeń wpisz wartość.
    * Wprowadź opis czynności, które trzeba wykonać, aby zmniejszyć ryzyko związane z zabezpieczeniami. Można na przykład ograniczyć ryzyko poprzez wykonanie bardziej szczegółowych przeglądów procesu, przeprowadzanie co miesiąc przeglądu menedżerskiego lub udostępnienie zasobów innym działom.  
13. Kliknij przycisk Zapisz.


