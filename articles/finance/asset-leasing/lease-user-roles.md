---
title: Przypisywanie ról użytkownikom w wynajmie
description: W tym artykule opisano role zabezpieczeń, które są używane w module Wynajem składnika majątku. Opisano tu również sposób przypisywania użytkowników do tych ról.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 38c859d64742d582d0709506d83600ea26a21147
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878139"
---
# <a name="assign-lease-user-roles"></a>Przypisywanie ról użytkownikom w wynajmie

[!include [banner](../includes/banner.md)]

W tym artykule opisano role zabezpieczeń, które są używane w module Wynajem składnika majątku. Opisano tu również sposób przypisywania użytkowników do tych ról.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
