desc "Install dependencies"
task :init do
  exec "ansible-galaxy install --ignore-errors --force " \
    " --role-file=ansible_galaxy_dependencies.txt"
end

desc "Upgrade to wheezy"
task :prepare do
  exec "ansible-playbook 000_prepare_wheezy.yml -l cloud"
end

desc "Install common utitilies"
task :common do
  exec "ansible-playbook 001_common_utilities.yml"
end

desc "Add SSH keys from GitHub"
task :github_keys do
  exec "ansible-playbook 002_ssh_keys_from_github.yml -l cloud"
end

desc "Set swap on"
task :swapon do
  exec "ansible-playbook 003_swapon.yml"
end

desc "Install Countly server"
task :countly do
  exec "ansible-playbook 012_countly.yml -l countly"
end

desc "Install GitLab server"
task :gitlab do
  exec "ansible-playbook 010_gitlab.yml -l gitlab"
end

desc "Install Jenkins server"
task :jenkins do
  exec "ansible-playbook 011_jenkins.yml -l jenkins"
end

desc "Install cow server"
task :cow do
  exec "ansible-playbook 020_cow_backend.yml"
end

desc "Install shadowsocks server"
task :shadowsocks do
  exec "ansible-playbook 022_shadowsocks.yml"
end

desc "Install Ghost"
task :ghost do
  exec "ansible-playbook 030_ghost.yml -l ghost"
end

desc "Test"
task :test do
  exec "vagrant up --no-provision && vagrant provision"
end