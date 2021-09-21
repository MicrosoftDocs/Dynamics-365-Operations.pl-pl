---
title: Ilość jest nieprawidłowa podczas rejestrowania zamówień przychodzących
description: 'Jeśli ilość przydzielona do numeru rejestracyjnego przekracza ilość, która nadal musi zostać odebrana, zostanie wyświetlony komunikat o błędzie: „Ilość jest nieprawidłowa”.'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477348"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>Ilość na numerze identyfikacyjnym jest nieprawidłowy podczas rejestrowania zamówień przychodzących

## <a name="symptoms"></a>Objawy

Podczas rejestrowania zamówień przychodzących może pojawić się następujący komunikat o błędzie:

> Ilość jest nieprawidłowa.

Jeśli w polu **Zasady grupowania identyfikatorów** jest ustawiona wartość *Zdefiniowane przez użytkownika* dla elementu menu urządzenia przenośnego używanego do rejestrowania zamówień przychodzących, pojawia się ten komunikat o błędzie i nie można dokończyć rejestracji.

## <a name="cause"></a>Powód

Gdy *Zdefiniowana przez użytkownika* jest używana jako zasada grupowania numerów identyfikacyjnych, system rozdziela przychodzące zapasy na osobne numery identyfikacyjne, zgodnie z grupą sekwencji jednostek. Jeśli do śledzenia otrzymywanego towaru używane są numery partii lub serii, ilości każdej partii lub serii należy określić zgodnie z zarejestrowanym numerem identyfikacyjnym. Jeśli ilość określona dla numeru rejestracyjnego przekracza ilość, która nadal musi zostać odebrana dla bieżących wymiarów, zostanie wyświetlony ten komunikat o błędzie.

## <a name="resolution"></a>Rozwiązanie

Podczas rejestrowania towaru za pomocą elementu menu urządzenia przenośnego, w którym w polu **Zasady grupowania numerów identyfikacyjnych** jest ustawiona wartość *Zdefiniowana przez użytkownika*, system może wymagać potwierdzenia lub wprowadzenia numerów identyfikacyjnych, numerów partii lub numerów seryjnych.

Na stronie potwierdzenia dla bieżącego numeru identyfikacyjnego system pokazuje ilość zaalokowana dla bieżącego numeru identyfikacyjnego. Na stronach potwierdzenia przetwarzania wsadowego lub seryjnego w systemie będzie pokazywana ilość, jaka musi zostać jeszcze odebrana dla bieżącego numeru seryjnego. Zawiera również pole, w którym można wprowadzić ilość do rejestracji dla tej kombinacji numeru identyfikacyjnego i numeru seryjnego. W tym przypadku upewnij się, że ilość zarejestrowana dla tego numeru identyfikacyjnego nie przekracza ilości, która musi być jeszcze otrzymana.

Jeśli podczas rejestracji zamówienia przychodzącego generowana jest zbyt wiele numerów identyfikacyjnych, wartość pola **Zasady grupowania numerów identyfikacyjnych** może zostać zmieniona na *Grupowanie numerów identyfikacyjnych*, można przypisać do towaru nową grupę sekwencji jednostek lub można dezaktywować opcję **Grupowania numerów identyfikacyjnych** dla tej grupy sekwencji jednostek.
