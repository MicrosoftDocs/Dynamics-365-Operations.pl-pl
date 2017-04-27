---
title: "Przegląd faktur od dostawcy"
description: "Ten artykuł zawiera ogólne informacje o fakturach od dostawców. Faktur od dostawców są wnioskami o płatność za produkty i usługi, które zostały odebrane. Faktury od dostawców mogą dotyczyć usług świadczonych w sposób ciągły albo bazować na zamówieniach zakupu za określone towary i usługi."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: bc6fb66e9038612cc133dc89e60eb3cb75cc7943
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-invoices-overview"></a>Przegląd faktur od dostawcy

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera ogólne informacje o fakturach od dostawców. Faktur od dostawców są wnioskami o płatność za produkty i usługi, które zostały odebrane. Faktury od dostawców mogą dotyczyć usług świadczonych w sposób ciągły albo bazować na zamówieniach zakupu za określone towary i usługi. 

<a name="vendor-invoices"></a>Faktury dostawcy
---------------

Faktura od dostawcy z zamówienia zakupu jest tworzona po odebraniu produktu lub usługi zgodnie z zamówieniem zakupu, które zostało założone u dostawcy. Faktura od dostawcy zawiera nagłówek oraz jeden lub więcej wierszy dla towarów lub usług. Faktura od dostawcy kończy cykl od zamówienia zakupu po przyjęcie produktów i fakturę od dostawcy. 

Mimo że niektóre faktury od dostawcy są powiązane z zamówieniem zakupu, faktury od dostawcy mogą także zawierać wiersze, które nie odnoszą się do wierszy zamówienia zakupu. Można też tworzyć faktury od dostawcy, które nie są związane z żadnymi zamówieniami zakupu. Te faktury od dostawcy mogą odzwierciedlać trwające usługi, np. rachunek za usługi komunalne, i nie muszą odnosić się do zamówienia zakupu, gdy je dodajesz. 

Istnieje kilka sposobów wprowadzania danych faktury od dostawcy:

-   Rejestr faktur od dostawcy umożliwia szybkie wprowadzanie faktur, które nie odwołują się do zamówienia zakupu, dzięki czemu można naliczać wydatki. Za pomocą arkusza zatwierdzania faktur od dostawcy można wybrać faktury i zaksięgować je na saldzie dostawcy w celu wycofania naliczonych kwot.
-   Arkusz faktur od dostawcy umożliwia szybkie wprowadzanie faktur, które nie odwołują się do zamówienia zakupu.
-   Wraz z pulą faktur od dostawcy rejestr faktur od dostawcy umożliwia szybkie wprowadzanie faktur do naliczania wydatku. Później można otworzyć powiązane zamówienia zakupu w celu zaksięgowania faktury na koncie wydatków.
-   Na stronach **Otwarte faktury od dostawcy** i **Oczekujące faktury od dostawcy** można utworzyć faktury od dostawcy z potwierdzonych zamówień zakupu.

Poniżej znajdziesz więcej informacji o używaniu stron **Otwarte faktury od dostawcy** lub **Oczekujące faktury od dostawcy** do tworzenia faktury od dostawcy z zamówienia zakupu.

## <a name="understanding-invoice-line-quantities"></a>Zrozumienie ilości w wierszach faktury
Po otwarciu faktury od dostawcy z pokrewnego zamówienia zakupu, wiersze faktury są tworzone na podstawie zamówienia zakupu. Domyślnie ilości są pobierane z ilości dokumentu przyjęcia produktów. Można jednak użyć jednego z następujących zachowań domyślnych:

-   **Ilość dostarczana teraz** — należy stosować w przypadku dostaw częściowych. Domyślna ilość w polu **Ilość** jest pobierana z pola ilości **Dostarczone teraz** z zamówienia zakupu.
-   **Zamówiona ilość** — ta opcja jest dla dostaw pełnych. Domyślna wartość w polu ** Ilość** jest pobierana z pola ilości **Zamówione** z zamówienia zakupu.
-   **Zarejestrowana ilość** — Użyj tej opcji, jeśli towar wymaga zarejestrowania, jak określono na stronie **grup modeli towarów**. Domyślną wartością w polu **Ilość** jest fizyczna zaktualizowana ilość, która została zarejestrowana.
-   **Ilość na dokumencie przyjęcia produktów** — ta opcja jest używana, jeżeli został już otrzymany dokument przyjęcia produktów dla zamówienia. Domyślna wartość w polu **Ilość** jest określana na podstawie łącznej ilości w dostępnych dokumentach przyjęcia produktów.
-   **Zarejestrowane ilości i usługi** — zaznacz tę opcję, jeśli zostały zarejestrowane ilości w arkuszach przyjęć towarów magazynowanych lub towarów, które nie są magazynowane. Ta opcja dotyczy także usług, niezależnie od tego, czy są zarejestrowane.

Jeśli z firma używa uzgadniania faktur, można wyświetlić wyniki uzgadniania ilości w kolumnie **Dopasowanie ilości dokumentów przyjęcia produktów**. Można również użyć polecenia **Szczegóły uzgadniania** na karcie **Przegląd** kartę, aby wyświetlić wyniki uzgadniania ilości.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Dodanie wiersza, którego nie było w zamówieniu zakupu
Można dodać nowy wiersz, którego nie było w zamówieniu zakupu, do faktury od dostawcy. Należy wybrać kategorię zaopatrzenia lub numer towaru. Następnie można dodać ilości, ceny i kwoty do wiersza. Wiersz zostanie uwzględniony tylko w regułach uzgadniania dla sumy faktury.

## <a name="submitting-a-vendor-invoice-for-review"></a>Przesyłanie faktury od dostawcy do przeglądu
Organizacja może używać przepływu pracy do zarządzania procesem przeglądu faktur od dostawców. Przegląd za pomocą przepływu pracy może być wymagany dla nagłówka faktury i/lub wiersza faktury. Formanty przepływu pracy są stosowane do nagłówka lub wiersza, w zależności od tego, gdzie był ustawiony fokus przed kliknięciem formantu. Zamiast przycisku **Księguj** widoczny będzie przycisk **Prześlij**, który służy do wysyłania przez proces przeglądu faktury od dostawcy.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Uzgadnianie faktur od dostawców z dokumentami przyjęcia produktów
Można wprowadzić i zapisać informacje o fakturach od dostawcy oraz uzgodnić wiersze faktur z wierszami dokumentów przyjęcia produktów. Można także uzgadniać ilości częściowe dla wiersza. 

Można utworzyć fakturę od dostawcy na podstawie pozycji dokumentu przyjęcia produktów, które zostały dotychczas otrzymane, nawet jeśli wszystkie elementy dla konkretnego zamówienia zakupu nie zostały jeszcze otrzymane. Można to zrobić na przykład w sytuacji, jeśli dostawca wysyła jedną fakturę na miesiąc, która pokrywa wszystkie dostawy wysłane przez niego w ciągu tego miesiąca. Każdy dokument przyjęcia produktów reprezentuje częściową lub kompletną dostawę towarów dla zamówienia zakupu. 

W momencie zaksięgowania faktury ilość **Pozostałe do zafakturowania** dla każdego towaru jest aktualizowana łączną sumą otrzymanych sztuk z wybranych dokumentów przyjęcia produktów. Jeśli obydwie wartości **Pozostałe do zafakturowania** i **Pozostałe do dostarczenia** dla wszystkich towarów z zamówienia zakupu są zerowe (0), to zamówienie zakupu otrzymuje stan **Zafakturowane**. Jeśli ilość **Pozostałe do zafakturowania** jest równa zero (0), stan zamówienia zakupu nie zmienia się i mogą być wprowadzane kolejne faktury.

Ta opcja zakłada, że przynajmniej jeden dokument przyjęcia produktów został zaksięgowany dla danego zamówienia zakupu. Faktura od dostawcy jest oparta na takich właśnie dokumentach przyjęcia produktów i odzwierciedla wielkości dostaw. Dane finansowe do faktury są oparte na informacjach wprowadzonych podczas księgowania faktury.

## <a name="working-with-multiple-invoices"></a>Korzystanie z wielu faktur

Można pracować z wieloma fakturami w tym samym czasie i księgować je wszystkie równocześnie. Jeśli zachodzi potrzeba utworzenia wielu faktur, użyj strony **oczekujących faktur od dostawcy**. Jeśli musisz zaksięgować i wydrukować wiele faktur od dostawcy, użyj strony arkusza zatwierdzania faktur. Jeśli używasz arkusza zatwierdzania faktur, przynajmniej jeden dokument przyjęcia produktów musi być zaksięgowany dla zamówienia zakupu oraz faktura dla zamówienia zakupu musi być zaksięgowana w rejestrze faktur. Informacje finansowe dla faktury pochodzą z faktury, która została zaksięgowana w rejestrze.





