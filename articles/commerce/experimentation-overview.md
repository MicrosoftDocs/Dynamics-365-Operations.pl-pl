---
title: Eksperymentowanie w programie Dynamics 365 Commerce
description: Eksperymentowanie umożliwia tworzenie i edytowanie układu strony i zawartości w konstruktorze witryn oraz zarządzanie nimi. Obsługa kompleksowych eksperymentów jest włączona dla stron i jednostek handlu elektronicznego na stronie.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 292a8934e735c76389e36603a708fd2a1bbf7691
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986548"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Eksperymentowanie w programie Dynamics 365 Commerce
Eksperymentowanie w Dynamics 365 Commerce pozwala sprawdzić skuteczność stron handlu elektronicznego i podjęcie decyzji na podstawie danych. Program Commerce obsługuje testy A/B na stronach, modułach i fragmentach oraz umożliwia mierzenie wpływu proponowanych zmian w witrynie internetowej.

W konstruktorze witryn Commerce można tworzyć, edytować i zarządzać elementami stron i zawartości, znanymi jako **odmiany**. Commerce jest integrowany z usługami innych firm, które mogą być używane do tworzenia eksperymentów i przypisań. Strumienie zdarzeń w czasie rzeczywistym przechwycone w module Commerce umożliwiają analizę, która definiuje wyniki eksperymentu w usłudze innej firmy. Następnie można skorzystać z tych analiz, aby uzyskać pomoc techniczną lub zakwestionować hipotezę.

## <a name="set-up-prerequisites"></a>Ustawianie wymagań wstępnych
1. **Pobierz poprawną wersję modułu Commerce**— uaktualnij bibliotekę modułów, zestaw Software Development Kit SDK rozbudowy kanału online oraz Commerce Scale Unit do wersji Commerce 10.0.13 lub nowszej.
1. **Konfigurowanie łącznika eksperymentów** — łącznik eksperymentów umożliwia systemowi Commerce nawiązywanie połączenia z usługami innych firm w celu pobrania listy eksperymentów i ustalenia, kiedy należy pokazywać użytkownikowi eksperyment. Można zakupić łącznik innej firmy w [AppSource](https://appsource.microsoft.com). Postępuj zgodnie z instrukcjami konfiguracji dostarczonymi przez wydawcę. Można alternatywnie skorzystać z przykładowego łącznika testowego z modułu Commerce, aby przetestować przepływ pracy eksperymentowania bez konieczności konfigurowania usługi zewnętrznej. Aby uzyskać więcej informacji, zobacz temat [Konfiguracja i włączanie łączników](e-commerce-extensibility/connectors.md). 
1. **Włącz flagi funkcji eksperymentowania w Commerce** — możesz włączyć eksperymentowanie na poziomie dzierżawy, przechodząc do **Ustawienia dzierżawy > Funkcje** lub w **Ustawienia witryny > Funkcje**.
    - Włącz flagę **Eksperymentowanie**, aby utworzyć eksperymenty dotyczące różnych modułów na stronie bez wpływu ani kopiowania innej zawartości, która nie jest częścią eksperymentu. Powoduje to, że ciągłe aktualizacje zawartości poza eksperymentem są zsynchronizowane w czasie trwania eksperymentu. Wyłączenie tej flagi powoduje zatrzymanie wszystkich eksperymentów pokazywanych użytkownikom i usunięcie wszystkich funkcji edycji w ramach konstruktora witryn.
    - Włączenie flagi **Eksperymenty na stronach lub fragmentach** umożliwia uruchamianie eksperymentów na stronie lub fragmencie. Spowoduje to utworzenie pełnej kopii wystąpienia całej strony lub fragmentu dla wszystkich modułów w obrębie strony lub fragmentu. Tego trybu należy używać, gdy konieczne jest testowanie obszernych zmian zawartości lub synchronizowanie ciągłej zmiany zawartości między wystąpieniami nie jest problemem. Wyłączenie tej flagi zapobiega tworzeniu i edytowaniu nowych eksperymentów na stronach i fragmentach.
    > [!NOTE]
    > Flaga **Eksperymentowanie** musi również być włączona, aby można było korzystać z funkcji **Eksperymenty na stronach lub fragmentach**.
    
## <a name="experimentation-lifecycle"></a>Cykl życia eksperymentowania
Konfigurowanie eksperymentu, tworzenie odmian i uruchamianie eksperymentu jest procesem iteracyjnym. Poniższy diagram przedstawia czas trwania eksperymentowania w Commerce i usłudze innej firmy. 

[ ![Cykl życia eksperymentowania.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Więcej informacji na temat każdego kroku procesu eksperymentowania można znaleźć w poniższych tematach.
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