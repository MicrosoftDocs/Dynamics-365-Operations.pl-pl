---
title: Konfigurowanie podziału obowiązków
description: Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c1521d6bbbe12964fef0942fcc4943f12a4360a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562504"
---
# <a name="set-up-segregation-of-duties"></a>Konfigurowanie podziału obowiązków

[!include [banner](../../includes/banner.md)]

Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników. Ta koncepcja jest nazywana podziałem obowiązków. Na przykład można nie chcieć, aby ta sama osoba potwierdzała przyjęcie towarów i przetwarzała płatność dla dostawcy. Podział obowiązków pomaga zmniejszyć ryzyko oszustwa, a także wykrywać błędy lub nieprawidłowości. Podział obowiązków może także służyć do wymuszania zasad kontroli wewnętrznej. Aby utworzyć regułę, wykonaj procedurę opisaną poniżej. W celu wykonania procedury musisz być administratorem systemu.

1. Wybierz kolejno opcje **Administrowanie systemem** > **Zabezpieczenia** > **Podział obowiązków** > **Reguły podziału obowiązków**.
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

> [!IMPORTANT] 
> Podczas tworzenia reguły nie jest sprawdzana zgodność z regułami podziału obowiązków. Można utworzyć regułę, która powoduje konflikt z istniejącymi rolami. Istniejące przypisania ról użytkowników mogą także kolidować z nową regułą. Po utworzeniu lub zmodyfikowaniu reguły należy zweryfikować zgodność. Aby uzyskać więcej informacji, zobacz temat [Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków](identify-resolve-conflicts-segregation-duties.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]