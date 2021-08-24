---
title: Księgowanie za pomocą ksiąg pochodnych
description: W tym artykule opisano sposób korzystania z ksiąg pochodnych.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f76b30ebf61e0fc709513d1f5a1670930fab54a51d976df80842c35a2ae10b63
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754249"
---
# <a name="post-with-derived-books"></a>Księgowanie za pomocą ksiąg pochodnych

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób korzystania z ksiąg pochodnych.

W przypadku księgowania transakcji w księdze, która zawiera księgi pochodne, transakcje w księgach pochodnych są księgowane automatycznie z arkuszy, zamówień zakupu i faktur niezależnych. Jeżeli jednak przygotowujesz transakcje dla księgi podstawowej w arkuszu Środki trwałe, możliwe będzie wyświetlanie i modyfikowanie kwot transakcji pochodnych przed ich zaksięgowaniem.
-   Pewne konta, takie jak konto podatkowe, konto odbiorcy lub konto dostawcy, są aktualizowane tylko raz poprzez księgowanie w księdze podstawowej. Transakcje księgi pochodnej są księgowane na kontach zdefiniowanych dla księgi pochodnej na stronie Profile księgowania środków trwałych.
-   Dla ksiąg pochodnych jako typ transakcji jest zwykle używana opcja Nabycie. Z tej opcji można korzystać, jeżeli księga i księga pochodna mają być stosowane dla środków trwałych od momentu ich nabycia.
-   Możliwe jest także stosowanie innych wartości dla opcji typu transakcji. Na przykład jeżeli w księgach podstawowej i pochodnych są te same okresy dotyczące sprzedaży lub likwidacji, wszystkie typy transakcji na środkach trwałych są dostępne podczas konfigurowania księgi pochodnej.

> [!WARNING]
> Amortyzacja zaksięgowana w księdze pochodnej będzie na tę samą kwotą, co kwota zaksięgowana w księdze podstawowej. Jeżeli metody amortyzacji są różne w obu rodzajach ksiąg, nie należy generować transakcji amortyzacji za pomocą procesu ksiąg pochodnych. |

## <a name="example"></a>Przykład 
Na podstawie poniższych informacji prześledźmy sposób konfigurowania transakcji nabycia przy użyciu funkcji ksiąg pochodnych.

1.  Utwórz księgi na stronie Księgi.
    -   Księga do celów księgowych: VM 1, warstwa księgowania Bieżący
    -   Księga do celów podatkowych: VM 2, warstwa księgowania Podatek

2.  W obszarze VM 1 kliknij kartę Księgi pochodne. Wybierz opcję VM 2 w polu Księga i opcję Nabycie w polu Typ transakcji.

Księgi można dołączać do określonych środków trwałych. 

Jeżeli nabycie środka trwałego zostanie zaksięgowane w księdze VM 1, nie zostanie zaksięgowane tylko w księdze VM 1, ale również w księdze pochodnej VM 2. Stan obu ksiąg środków trwałych zmieni się na Otwarty.

> [!NOTE]                                                                                                         
> Jeżeli nie jest używana funkcja ksiąg pochodnych, należy zaksięgować nabycie środka trwałego osobno w księgach VM 1 i VM 2.

Aby uzyskać więcej informacji, zobacz [Księgi pochodne](derived-books.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]