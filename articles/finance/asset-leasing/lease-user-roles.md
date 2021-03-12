---
title: Przypisywanie ról użytkownikom w wynajmie
description: W tym temacie opisano role zabezpieczeń, które są używane w module Wynajem składnika majątku. Opisano tu również sposób przypisywania użytkowników do tych ról.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: df23e219f5bd859b0072785dfd5f7a0ec63f540e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995400"
---
# <a name="assign-lease-user-roles"></a>Przypisywanie ról użytkownikom w wynajmie

[!include [banner](../includes/banner.md)]

W tym temacie opisano role zabezpieczeń, które są używane w module Wynajem składnika majątku. Opisano tu również sposób przypisywania użytkowników do tych ról.

Trzy role użytkowników różnicują dostęp w module Wynajem składnika majątku. Jedna rola jest odpowiednia do obsługi umów wynajmu, jedna jest odpowiednia do przeglądania umów wynajmu, a jedna jest odpowiednia do wykonywania obowiązków pracownika wykonującego umowy leasingu. Każda rola ma określone uprawnienia dla wszystkich stron dokumentu umowy leasingu oraz pozwala użytkownikom wyświetlać, tworzyć, edytować i usuwać umowy wynajmu, zgodnie z ich służbowymi obowiązkami.

| Rola           | opis |
|----------------|-------------|
| Obsługa wynajmu | Użytkownicy w tej roli mogą dodawać, edytować, usuwać i wyświetlać umowy wynajmu. Ta rola jest przeznaczona dla użytkowników, których codzienne zadania obejmują tworzenie i księgowanie miesięcznych wpisów w arkuszach oraz dodawanie nowych umów wynajmu. Ta rola daje dostęp do wszystkich funkcji modułu Obsługa wynajmu. |
| Wyświetl wynajem     | Użytkownicy w tej roli mogą tylko wyświetlać rekordy umowy wynajmu i harmonogramy oraz generować raporty. Nie mogą tworzyć nowych umów wynajmu, edytować istniejących umów wynajmu ani tworzyć wpisów w arkuszach dla umów wynajmu. Ta rola jest przeznaczona dla użytkowników, którzy potrzebują tylko wglądu w umowy wynajmu, harmonogramy i transakcje dotyczące tych umów wynajmu. |
| Pracownik wynajmu    | Użytkownicy w tej roli mogą tylko tworzyć nowe umowy wynajmu. Nie mogą edytować ani usuwać istniejących umów wynajmu, wyświetlać harmonogramów umów wynajmu ani księgować wpisów w arkuszu wynajmu. Ta rola jest przeznaczona dla użytkowników zajmujących się wprowadzaniem danych. |

Aby przypisać użytkowników do ról używanych w module Wynajem składnika majątku, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Administrowanie systemem \> Zabezpieczenia \> Przypisywanie użytkowników do ról**.
2. Wybierz rolę **Obsługa wynajmu**, **Pracownik wynajmu** lub **Wyświetl wynajem**, a następnie wybierz opcję **Ręcznie przypisz/wyklucz użytkowników**.
3. Wybierz użytkownika, który ma zostać przypisany do roli, a następnie wybierz opcję **Przypisz do roli**.
