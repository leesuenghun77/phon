# phon
배터리 소모가 덜 되도록
import os
import datetime

# 백그라운드 앱 및 프로세스 관리
def manage_background_apps():
    # 불필요한 백그라운드 앱 강제 종료
    os.system("am kill-all")
    
    # 자동 동기화, 위치 서비스 비활성화
    os.system("settings put global auto_sync 0")
    os.system("settings put secure location_mode 0")

# 디스플레이 설정 최적화    
def optimize_display_settings():
    # 화면 밝기 조절
    os.system("settings put system screen_brightness 50")
    
    # 화면 자동 꺼짐 시간 설정
    os.system("settings put system screen_off_timeout 60000")
    
    # 야간 모드 활성화
    os.system("settings put global night_display_activated 1")

# 네트워크 관리
def manage_network():
    # Wi-Fi 및 블루투스 끄기
    os.system("svc wifi disable")
    os.system("svc bluetooth disable")
    
    # 모바일 데이터 사용 최소화
    os.system("svc data disable")
    
    # 자동 동기화 기능 끄기
    os.system("settings put global auto_sync 0")

# 배터리 최적화 앱 활용
def use_battery_optimizer():
    # 배터리 최적화 앱 실행
    os.system("am start -n com.android.settings/.fuelgauge.BatteryInfo")

# 스크립트 실행
if __name__ == "__main__":
    print(f"배터리 최적화 스크립트 실행 시간: {datetime.datetime.now()}")
    manage_background_apps()
    optimize_display_settings()
    manage_network()
    use_battery_optimizer()
    print("배터리 최적화가 완료되었습니다.")
