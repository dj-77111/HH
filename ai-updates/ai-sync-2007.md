UPDATE users 
SET last_login = NOW(), 
    login_attempts = login_attempts + 1 
WHERE username = 'admin' AND is_active = TRUE; 

COMMIT; 

INSERT INTO login_history (username, login_time, ip_address) 
VALUES ('admin', NOW(), '192.168.1.100'); 

COMMIT;