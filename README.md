# Fragment_Lifecycle

Fragment 생성 -> onAttach() -> onCreate() -> onCreateView() -> onActivityCreated() -> onStrat() -> onResume() -> Fragment is Active 


-> onPause() -> onStop() -> onDestroyView() -> onDetach()  -> Fragment is destroyed 

onDestroyed ---> onCreateView : The Fragment returns to the layout from the back stack

onCreate() :  
프래그먼트를 생성할 때 호출한다. 
프래그먼트가 일시정지 혹은 중단 후 재개되었을 때, 유지하고 있어야 하는 것을 여기서 초기화 해야한다.

onCreateView() :
프래그먼트가 자신의 인터페이스를 처음 그리기 위해 호출한다. 
View를 변환해야 한다. 
이 메서드는 프래그먼트의 레이아웃 루트이기 때문에 UI를 제공하지 않는 경우에는 null을 반환하면 된다. 

onPause() : 
사용자가 프래그먼트를 떠나면 첫번 째로 이 메서드를 호출한다.
사용자가 돌아오지 않을 수도 있으므로 여기에 사용자 세션을 넘어 지속되어야 하는 변경사항을 저장한다.

onResume() :
이 상태에 들어갔을 때, 사용자와 상호작용 한다. 
어떤 이벤트가 발생하여 포커스가 떠날 때 까지 이 상태에 머무른다. 
프로그램이 일시정지되어 onPause()를 호출하고 다시 재개되면 onResume() 메서드를 다시 호출한다. 
재개 상태로 전환될때마다 필요한 초기화 작업들을 수행해야 한다.

onStop() : 
프래그먼트가 보이지 않는다. 
호스트 액티비티가 정지되었거나 프래그먼트가 액티비티에서 제거되었지만 Back Stack에 추가된다.
정지된 프래그먼트의 모든 상태 및 멤버 정보는 보존된다. 
하지만 사용자에게는 더이상 표시 되지 않으며 액티비티를 종료하면 프래그먼트도 종료된다.
