---
title: Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków
description: Ten temat wyjaśnia, jak identyfikować i rozwiązywać konflikty w podziale obowiązków.
author: peakerbl
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ebd59c7018a50e01253697d792698664a981566
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745820"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków

[!include [banner](../../includes/banner.md)]

Ten temat wyjaśnia, jak identyfikować i rozwiązywać konflikty w podziale obowiązków. Można ustawić reguły rozdzielania obowiązków, które mają być wykonywane przez różnych użytkowników. Ta koncepcja jest nazywana podziałem obowiązków. Gdy definicja roli zabezpieczeń lub przypisanie ról użytkownika naruszają reguły, jest rejestrowany konflikt. Wszystkie konflikty muszą być rozwiązane przez administratora. Aby zidentyfikować i rozwiązać konflikty, wykonaj procedurę opisaną poniżej.

Po dodaniu reguły sprawdź, czy wszystkie istniejące role są zgodne. 

## <a name="verify-that-existing-roles-and-duties-comply-with-new-rules-for-segregation-of-duties"></a>Sprawdzanie, czy istniejące role i obowiązki są zgodne z nowymi regułami podziału obowiązków
1. Wybierz kolejno opcje **Administrowanie systemem** > **Zabezpieczenia** > **Podział obowiązków** > **Reguły podziału obowiązków**.
3. Wybierz **Sprawdź poprawność obowiązków i ról**. Jeśli którakolwiek rola narusza reguły, jest wyświetlany komunikat zawierający nazwę roli, rolę oraz nazwy obowiązków powodujących konflikt. Role powodujące konflikt muszą zostać zmodyfikowane za pomocą **konfiguracji zabezpieczeń** i nie mogą zawierać konfliktu obowiązków. Jeśli żadna rola nie narusza wybranej reguły, komunikat wskazuje, że wszystkie role wykazują zgodność.   

> [!NOTE]
> Walidacja jest wykonywana tylko dla wybranej reguły. Ważna jest walidacja zgodności poszczególnych reguł.   

Podczas tworzenia lub modyfikowania roli reguły podziału obowiązków są wymuszane automatycznie. Do roli nie można przypisać konfliktu obowiązków.

Następnie sprawdź, czy wszystkie istniejące przypisania ról są zgodne.

## <a name="verify-that-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Sprawdzanie, czy przypisania ról użytkowników są zgodne z nowymi regułami podziału obowiązków
1. Wybierz kolejno opcje **Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Sprawdź zgodność przypisań ról użytkownika**.
2. Kliknij przycisk **OK**. W powiadomieniu są wyświetlane wyniki sprawdzania poprawności. Konflikty są również zapisywane na stronie **Nierozwiązane konflikty podziału obowiązków**.   

Podczas przypisywania użytkowników do ról reguły podziału obowiązków są wymuszane automatycznie. W przypadku próby przypisania użytkownika do ról zawierających obowiązki powodujące konflikt, zostanie wyświetlony komunikat o błędzie. Następnie należy rozwiązać ten konflikt, odmawiając lub zezwalając na przypisanie dodatkowej roli. Rola dodatkowa zostanie przypisana, gdy będzie dozwolone przypisanie. 

> [!NOTE]
> Konflikty nie zostały obecnie zweryfikowane dla użytkowników, którzy są przypisani do ról na podstawie grup domen usługi Active Directory.

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Wyświetlanie i rozwiązywanie konfliktów z przypisaniami ról użytkowników
1. Wybierz kolejno opcje **Administrowanie systemem** > **Zabezpieczenia** > **Podział obowiązków** > **Nierozwiązane konflikty podziału obowiązków**. 
2. Wybierz konflikt, a następnie wybierz jedną z następujących akcji: 

  - **Odmów przypisania**: spowoduje to odmowę przypisania użytkownika do dodatkowej roli zabezpieczeń. Jeśli nie pozwolisz na automatyczne przypisanie roli, użytkownik jest oznaczany jako wykluczony z roli. Wykluczonemu użytkownikowi nie jest przyznawany dostęp skojarzony z rolą. Nie może on otrzymać roli, dopóki administrator nie usunie wykluczenia. 
-  **Zezwalaj na przypisanie**: spowoduje to zignorowanie konfliktu i pozwolenie na przypisanie użytkownika do dodatkowej roli zabezpieczeń. Jeśli zignorujesz konflikt, musisz wprowadzić przyczynę w polu **Przyczyna zastąpienia**. Wszystkie zastąpione przypisania roli można wyświetlić na stronie **Konflikty podziału obowiązków**.  

> [!NOTE]
> Jeśli dla tego samego użytkownika zostanie wymienionych kilka konfliktów, wybierz rekord użytkownika i oszacuj przypisane role na stronie **Użytkownicy**. Aby uniknąć konfliktu, należy sprawdzić poprawność każdej reguły po jej dodaniu lub zmodyfikowaniu.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]