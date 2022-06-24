---
title: Eksperymentowanie w programie Dynamics 365 Commerce
description: Eksperymentowanie umożliwia tworzenie i edytowanie układu strony i zawartości w konstruktorze witryn oraz zarządzanie nimi. Obsługa kompleksowych eksperymentów jest włączona dla stron i jednostek handlu elektronicznego na stronie.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946221"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Eksperymentowanie w programie Dynamics 365 Commerce
Eksperymentowanie w Dynamics 365 Commerce pozwala sprawdzić skuteczność stron handlu elektronicznego i podjęcie decyzji na podstawie danych. Program Commerce obsługuje testy A/B na stronach, modułach i fragmentach oraz umożliwia mierzenie wpływu proponowanych zmian w witrynie internetowej.

W konstruktorze witryn Commerce można tworzyć, edytować i zarządzać elementami stron i zawartości, znanymi jako **odmiany**. Commerce jest integrowany z usługami innych firm, które mogą być używane do tworzenia eksperymentów i przypisań. Strumienie zdarzeń w czasie rzeczywistym przechwycone w module Commerce umożliwiają analizę, która definiuje wyniki eksperymentu w usłudze innej firmy. Następnie można skorzystać z tych analiz, aby uzyskać pomoc techniczną lub zakwestionować hipotezę.

## <a name="set-up-prerequisites"></a>Ustawianie wymagań wstępnych

1. **Pobierz poprawną wersję modułu Commerce**— uaktualnij bibliotekę modułów, zestaw Software Development Kit SDK rozbudowy kanału online oraz Commerce Scale Unit do wersji Commerce 10.0.13 lub nowszej.
1. **Konfigurowanie łącznika eksperymentów** — łącznik eksperymentów umożliwia systemowi Commerce nawiązywanie połączenia z usługami innych firm w celu pobrania listy eksperymentów i ustalenia, kiedy należy pokazywać użytkownikowi eksperyment. Można zakupić łącznik innej firmy w [AppSource](https://appsource.microsoft.com). Postępuj zgodnie z instrukcjami konfiguracji dostarczonymi przez wydawcę. Można alternatywnie skorzystać z przykładowego łącznika testowego z modułu Commerce, aby przetestować przepływ pracy eksperymentowania bez konieczności konfigurowania usługi zewnętrznej. Aby uzyskać więcej informacji, zobacz temat [Konfiguracja i włączanie łączników](e-commerce-extensibility/connectors.md). 
1. **Włącz flagi funkcji eksperymentowania w Commerce** — możesz włączyć eksperymentowanie na poziomie dzierżawy, przechodząc do **Ustawienia dzierżawy \> Funkcje** lub w **Ustawienia witryny \> Funkcje**. Włącz flagę **Eksperymenty**, aby rozpocząć tworzenie wariantów modułu. Wyłączenie tej flagi powoduje zatrzymanie wszystkich eksperymentów pokazywanych użytkownikom i usunięcie wszystkich funkcji edycji w ramach konstruktora witryn.
    
## <a name="experimentation-lifecycle"></a>Cykl życia eksperymentowania

Konfigurowanie eksperymentu, tworzenie odmian i uruchamianie eksperymentu jest procesem iteracyjnym. Poniższy diagram przedstawia czas trwania eksperymentowania w Commerce i usłudze innej firmy. 

[ ![Cykl życia eksperymentowania.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Więcej informacji na temat każdego kroku procesu eksperymentowania można znaleźć w poniższych artykułach.
- [Określanie hipotezy i ustalanie metryki eksperymentu](experimentation-identify.md)
- [Konfigurowanie eksperymentu](experimentation-setup.md)
- [Łączenie i edytowanie eksperymentu](experimentation-connect-edit.md)
- [Podglądanie i publikowanie eksperymentu](experimentation-preview-publish.md)
- [Uruchamianie i monitorowanie eksperymentu](experimentation-run-monitor.md)
- [Podwyższenie poziomu i zakończenie eksperymentu](experimentation-review-complete.md)

> [!NOTE]
> Aby dowiedzieć się, gdzie eksperymentu znajduje się w cyklu życia **Eksperymenty** w konstruktorze witryn w okienku nawigacji po lewej stronie. Zostanie wyświetlona lista eksperymentów ze stanem każdego eksperymentu w Commerce i usłudze innej firmy. Aby uzyskać więcej informacji, zobacz temat [Sprawdzanie stanu eksperymentu](experimentation-status.md).

## <a name="next-step"></a>Następne kroki
[Określanie hipotezy i ustalanie metryki sukcesu eksperymentu](experimentation-identify.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
