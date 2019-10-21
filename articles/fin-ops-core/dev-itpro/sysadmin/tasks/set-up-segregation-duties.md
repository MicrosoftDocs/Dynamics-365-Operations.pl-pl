---
title: Konfigurowanie podziału obowiązków
description: Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40b40b77877680e28671b7a15ea8c8b58ce94417
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180882"
---
# <a name="set-up-segregation-of-duties"></a>Konfigurowanie podziału obowiązków

[!include [task guide banner](../../includes/task-guide-banner.md)]

Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników. Ta koncepcja jest nazywana podziałem obowiązków. Na przykład można nie chcieć, aby ta sama osoba potwierdzała przyjęcie towarów i przetwarzała płatność dla dostawcy. Podział obowiązków pomaga zmniejszyć ryzyko oszustwa, a także wykrywać błędy lub nieprawidłowości. Podział obowiązków może także służyć do wymuszania zasad kontroli wewnętrznej. Aby utworzyć regułę, wykonaj procedurę opisaną poniżej. W celu wykonania procedury musisz być administratorem systemu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DAT. 

1. Wybierz kolejno **okienko nawigacji > Moduły > Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Reguły podziału obowiązków**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa** wpisz wartość reguły.
4. W polu **Pierwszy obowiązek** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz pierwszy obowiązek, który będzie kontrolowany przez regułę.
6. W polu **Drugi obowiązek** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie. 
7. Na liście znajdź i zaznacz odpowiedni rekord. Wybierz drugi obowiązek, który będzie kontrolowany przez regułę.
10. W polu **Ważność** wybierz opcję. Wybierz priorytet ryzyka występującego wtedy, gdy ten sam użytkownik lub posiadacz roli wykonuje oba obowiązki.  
11. W polu **Ryzyko związane z zabezpieczeniami** wpisz wartość. Wprowadź opis ryzyka związanego z zabezpieczeniami.  
12. W polu **Ograniczenie zabezpieczeń** wpisz wartość. Wprowadź opis czynności, które trzeba wykonać, aby zmniejszyć ryzyko związane z zabezpieczeniami. Można na przykład ograniczyć ryzyko poprzez wykonanie bardziej szczegółowych przeglądów procesu, przeprowadzanie co miesiąc przeglądu menedżerskiego lub udostępnienie zasobów innym działom.     
13. Kliknij przycisk **Zapisz**.

