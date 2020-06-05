---
title: Przetwarzanie paragonów kosztowych
description: Ten temat zawiera informacje o przetwarzaniu za pomocą optycznego rozpoznawania znaków (OCR) dla paragonów. Ta funkcja ma na celu zwiększenie komfortu pracy użytkownika podczas tworzenia raportów z wydatków w Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 31c08ea264e6caec3217f4b424275495f39123e3
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378238"
---
# <a name="expense-receipt-processing"></a>Przetwarzanie przyjęcia wydatku

[!include [banner](../includes/banner.md)]

Wpisywanie wydatków zostało ulepszone przez wprowadzenie optycznego rozpoznawania znaków (OCR) do przetwarzania paragonów. Ta funkcja ma na celu zwiększenie komfortu pracy użytkownika podczas tworzenia raportów z wydatków.

## <a name="key-features"></a>Najważniejsze funkcje

- Nazwa handlowca, data i łączna kwota są wyodrębniane z paragonów.
- Funkcja próbuje dopasować niepołączone paragony do niepołączonych transakcji dotyczących wydatków.
- Użytkownicy mogą tworzyć ręcznie wprowadzone transakcje wydatków z paragonów.

## <a name="usage-examples"></a>Przykłady użycia

Aby automatycznie dołączać paragony, które uwzględniają transakcje karty kredytowej podczas tworzenia raportu z wydatków, wykonaj następujące czynności:

  1. Otwórz obszar roboczy **Zarządzanie wydatkami**.
  2. Na karcie **Przychody** sprawdź, czy istnieją niedołączone paragony. Możesz również wgrać paragony na karcie **Przychody**.
  3. Na karcie **Wydatki** sprawdź, czy istnieją niedołączone wydatki. Zazwyczaj administrator wydatków importuje te wydatki z danych od dostawcy karty kredytowej.
  4. Wybierz **Nowy raport o wydatkach**. Należy zauważyć, że po utworzeniu raportu o wydatkach można również uwzględnić wydatki i paragony. W przypadku dodania zarówno wydatków, jak i paragonów zostanie wyzwolone automatyczne dopasowywanie paragonów do wydatków.

Aby utworzyć wydatek lub dopasować wydatek z paragonu, wykonaj następujące czynności:

  1. W raporcie z wydatków na karcie **Paragony** dołącz paragon, zaznaczając opcję **Dodaj paragony**.
  2. W obszarze przekazanego obrazu paragonu zwróć uwagę na opcje **Utwórz** i **Powiąż**.

      - Wybierz opcję **Utwórz**, aby utworzyć ręcznie wprowadzaną transakcję wydatku, a następnie wypełnij wartości wyodrębnione z paragonu.
      - W przypadku wybrania opcji **Powiąż**, system próbuje dopasować istniejący wydatek do paragonu.

## <a name="installation"></a>Instalacja

Ta funkcja działa w połączeniu z **Funkcją wypracowania raportów z wydatków**, ułatwiającą uproszczenie pracy z wydatkami. Ta funkcja jest dostępna tylko dla środowisk w warstwie 2 i wyższych, które są w trybie piaskownicy i produkcji.

Aby skorzystać z tych zaawansowanych funkcji wydatków, należy zainstalować dodatek usługi zarządzania wydatkami dla rozwiązania Microsoft Dynamics 365 Finance i włączyć funkcje w wystąpieniu. Dostęp do dodatku można uzyskać z poziomu projektu w ramach usługi Microsoft Dynamics Lifecycle Services (LCS).

1. Zaloguj się do usługi LCS i otwórz żądane środowisko.
2. Przejdź do **Pełne szczegóły**.
3. Wybierz opcję **Zarządzaj** lub przewiń w dół do skróconej karty **dodatków środowiska**.
4. Wybierz opcję **Zainstaluj nowy dodatek**.
5. Wybierz **Usługę zarządzania wydatkami**.
6. Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.
7. Wybierz **Zainstaluj**.

W obszarze roboczym **Zarządzanie funkcjami** włącz następujące funkcje:

- Raporty wydatków w nowej wersji
- Automatyczne uzgadnianie i tworzenie wydatku z paragonu

Po włączeniu tych funkcji są wykonywane następujące akcje:

- Istniejący obszar roboczy **Zarządzania wydatkami** jest zastępowany nowym obszarem roboczym.
- Zostanie dodany nowy element menu widoczności pola wydatków.
- Można nadal otworzyć poprzednią stronę **Raportów z wydatków**, przechodząc do modułu **Zarządzanie wydatkami > Moje wydatki> Raporty o wydatkach**.
- Przepływy pracy i wszelkie zatwierdzenia nadal powodują przekierowanie do istniejącej strony raportów z wydatków.
- Paragony będą przetwarzane przez usługi poznawcze Microsoft Azure Cognitive Services, a metadane zostaną wyodrębnione i dodane.
- Dodawana jest opcja umożliwiająca utworzenie raportu z wydatków, który zawiera dopasowane niedołączone paragony.
- Opcja dodawana do raportów z wydatków umożliwia utworzenie wiersza wydatku na podstawie paragonu lub próbę dopasowania istniejącego paragonu do istniejącego wiersza wydatku.

Aby uzyskać więcej informacji o nowej funkcji wypracowywania raportów z wydatków, przejrzyj [Nowa funkcja analizowania raportów z wydatków](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Często zadawane pytania

**Czy firma Microsoft używa moich danych do swoich modeli?**

Nie, firma Microsoft opracowała ogólny model nauki dla usługi przetwarzania potwierdzeń odbioru. Ten model nie jest oparty na wgrywanych przez Ciebie paragonach.

**Gdzie jest dostępna i przetwarzana ta funkcja?**

Obecnie są obsługiwane Stany Zjednoczone.

**Gdzie przechodzą moje paragony?**

Finanse będą kontaktować się z usługami poznawczymi w celu wyodrębnienia danych z pól. Usługi poznawcze zachowają kopię paragonu do 24 godzin, podczas gdy trwać będzie przetwarzanie. Po zakończeniu przetwarzania, usługi poznawcze usuną paragon. Paragony nadal są przechowywane w Finance.

Aby uzyskać więcej informacji, przeczytaj temat [Włączanie funkcji rozpoznawania paragonów z nowymi możliwościami Form Recognizer](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
